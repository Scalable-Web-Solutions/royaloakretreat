<!-- FullscreenCarousel.svelte -->
<script lang="ts">
  import { onMount, onDestroy } from 'svelte';

  export let slides: { src: string; alt?: string }[] = [
    { src: 'https://static.wixstatic.com/media/1c989e_3e9aec50547d422f8454e13d272bce98~mv2.png/v1/fill/w_1905,h_1175,al_c,q_95,usm_0.66_1.00_0.01,enc_avif,quality_auto/1c989e_3e9aec50547d422f8454e13d272bce98~mv2.png', alt: 'Mountains at dawn' },
    { src: 'https://static.wixstatic.com/media/3cf872_47c6a3aec01143e28b3dd7749f233a61~mv2.png/v1/fill/w_1905,h_1175,al_c,q_95,usm_0.66_1.00_0.01,enc_avif,quality_auto/3cf872_47c6a3aec01143e28b3dd7749f233a61~mv2.png', alt: 'Workspace' },
    { src: 'https://static.wixstatic.com/media/1c989e_da993f58d54a46cc8b74ef78217ad18e~mv2.png/v1/fill/w_1905,h_1175,al_c,q_95,usm_0.66_1.00_0.01,enc_avif,quality_auto/1c989e_da993f58d54a46cc8b74ef78217ad18e~mv2.png', alt: 'Ocean' },
    { src: 'https://static.wixstatic.com/media/1c989e_b9dcee6fdff64dc4afdb3ee9460415d7~mv2.png/v1/fill/w_1905,h_1175,al_c,q_95,usm_0.66_1.00_0.01,enc_avif,quality_auto/1c989e_b9dcee6fdff64dc4afdb3ee9460415d7~mv2.png', alt: 'Mountains at dawn' },

  ];

  export let interval = 5000;

  let index = 0;
  let timer: any = null;
  let viewportEl: HTMLDivElement | null = null;
  let vw = 0; // set on mount

  const goto = (i: number) => (index = (i + slides.length) % slides.length);
  const next = () => goto(index + 1);
  const prev = () => goto(index - 1);

  const start = () => { stop(); timer = setInterval(next, interval); };
  const stop = () => { if (timer) clearInterval(timer); timer = null; };

  // these reference window only when mounted (we attach/remove in onMount/onDestroy)
  const handleKey = (e: KeyboardEvent) => {
    if (e.key === 'ArrowRight') next();
    if (e.key === 'ArrowLeft') prev();
  };

  const measure = () => {
    // avoid window during SSR; viewportEl exists only on client
    vw = viewportEl?.clientWidth ?? vw;
  };

  // drag/swipe
  let startX = 0;
  let deltaX = 0;
  let dragging = false;

  const onPointerDown = (e: PointerEvent) => {
    dragging = true;
    startX = e.clientX;
    deltaX = 0;
    stop();
    (e.target as HTMLElement)?.setPointerCapture?.(e.pointerId);
  };
  const onPointerMove = (e: PointerEvent) => {
    if (!dragging) return;
    deltaX = e.clientX - startX;
  };
  const onPointerUp = () => {
    if (!dragging) return;
    if (Math.abs(deltaX) > Math.max(50, vw * 0.12)) {
      deltaX < 0 ? next() : prev();
    }
    dragging = false;
    deltaX = 0;
    start();
  };

  let removeResize: (() => void) | null = null;
  let removeKey: (() => void) | null = null;

  onMount(() => {
    // safe to use window here
    vw = viewportEl?.clientWidth ?? window.innerWidth;

    const resize = () => {
      vw = viewportEl?.clientWidth ?? window.innerWidth;
    };
    window.addEventListener('resize', resize);
    window.addEventListener('keydown', handleKey);

    removeResize = () => window.removeEventListener('resize', resize);
    removeKey = () => window.removeEventListener('keydown', handleKey);

    start();
  });

  onDestroy(() => {
    stop();
    removeResize?.();
    removeKey?.();
  });
</script>

<!-- svelte-ignore a11y_no_static_element_interactions -->
<div
  class="carousel"
  bind:this={viewportEl}
  on:pointerdown={onPointerDown}
  on:pointermove={onPointerMove}
  on:pointerup={onPointerUp}
  on:pointercancel={onPointerUp}
  on:mouseleave={() => dragging && onPointerUp()}
  aria-roledescription="carousel"
>
  <div class="badge" aria-hidden="true">Our Vision</div>

  <div
    class="track"
    style="transform: translate3d({-(index * vw) + (dragging ? deltaX : 0)}px, 0, 0); transition: {dragging ? 'none' : 'transform 420ms cubic-bezier(.22,.61,.36,1)'};"
  >
    {#each slides as s, i}
      <figure class="slide" aria-hidden={i !== index} aria-label={`Slide ${i + 1} of ${slides.length}`}>
        <img src={s.src} alt={s.alt ?? ''} />
        <div class="scrim" />
      </figure>
    {/each}
  </div>

  <button class="nav prev" on:click={prev} aria-label="Previous slide">‹</button>
  <button class="nav next" on:click={next} aria-label="Next slide">›</button>

  <div class="dots" role="tablist" aria-label="Slide navigation">
    {#each slides as _, i}
      <!-- svelte-ignore element_invalid_self_closing_tag -->
      <button
        class="dot {i === index ? 'active' : ''}"
        role="tab"
        aria-selected={i === index}
        aria-label={`Go to slide ${i + 1}`}
        on:click={() => goto(i)}
      />
    {/each}
  </div>
</div>

<style>
  .carousel {
    position: relative;
    width: 100vw;
    height: 101.5vh;
    overflow: hidden;
    user-select: none;
    touch-action: pan-y;
    background: #000;
  }
  .badge {
    position: absolute;
    top: 1.25rem;
    left: 1.25rem;
    z-index: 3;
    padding: 0.5rem 0.9rem;
    font-weight: 600;
    letter-spacing: 0.02em;
    font-size: 24pt;
    color: white;
  }
  .track {
    display: flex;
    height: 100%;
    will-change: transform;
  }
  .slide { position: relative; min-width: 100%; height: 100%; }
  .slide img { width: 100%; height: 100%; object-fit: cover; display: block; }
  .scrim { position: absolute; inset: 0; background: linear-gradient(to top, rgba(0,0,0,0.35), rgba(0,0,0,0.15) 50%, rgba(0,0,0,0)); pointer-events: none; }
  .nav {
    position: absolute; top: 50%; transform: translateY(-50%); z-index: 3;
    width: 44px; height: 44px; border: none; border-radius: 9999px;
    background: rgba(255,255,255,0.8); color: #111; font-size: 28px; line-height: 1; cursor: pointer;
    display: grid; place-items: center; backdrop-filter: blur(6px);
  }
  .nav:hover { background: rgba(255,255,255,0.95); }
  .nav.prev { left: 14px; }
  .nav.next { right: 14px; }
  .dots { position: absolute; left: 50%; bottom: 16px; transform: translateX(-50%); display: flex; gap: 8px; z-index: 3; }
  .dot { width: 8px; height: 8px; border-radius: 9999px; border: none; background: rgba(255,255,255,0.55); cursor: pointer; }
  .dot.active { background: #fff; width: 18px; border-radius: 9999px; transition: width 200ms ease; }
</style>
