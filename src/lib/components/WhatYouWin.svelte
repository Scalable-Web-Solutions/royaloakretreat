<script lang="ts">
  export let id = '';

  const items = [
    {
      title: 'Wellness Centered Amenities',
      desc:
        'Start your morning with a private sauna or cold plunge—then nourish your body with handpicked recipes and thoughtfully sourced supplements.',
      src: 'https://static.wixstatic.com/media/1c989e_7277198225eb4c459d3bc7fd6f294ac0~mv2.png/v1/fill/w_600,h_1108,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/rear%20cold%20plunge%202.png'
    },
    {
      title: 'No schedules. No screens. Just presence.',
      desc:
        'From morning yoga to twilight dips in the hot tub—define your daily ritual with science-backed wellness tools at your fingertips.',
      src: 'https://static.wixstatic.com/media/1c989e_b2d698c12b9d41a09f867cd389aaadb3~mv2.png/v1/fill/w_600,h_1108,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/Sundress%20Lounger%202.png'
    },
    {
      title: 'All Paws Welcome',
      desc:
        'Forest trails and endless new smells—bring your dog along and enjoy the outdoors together.',
      src: 'https://static.wixstatic.com/media/1c989e_e34b699502684144b0ad095e4237a715~mv2.png/v1/fill/w_600,h_1108,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/what%20the%20dog%20doin.png'
    }
  ];
</script>

<section
  {id}
  class="mx-auto scroll-mt-24 min-h-screen w-full flex flex-col items-center justify-center
         bg-[url('https://static.wixstatic.com/media/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png/v1/fill/w_1450,h_1120,al_c,q_90,enc_avif,quality_auto/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png')]
         bg-cover"
>
  <!-- mobile: auto height; desktop: keep full-height feel -->
  <div class="backdrop-blur-xl flex flex-col justify-center w-full h-auto md:h-screen px-4 sm:px-6 md:px-8 py-12 sm:py-16 md:py-24">
    <div class="text-center max-w-2xl mx-auto px-2">
      <h2 class="text-3xl md:text-5xl font-serif">What We’re About</h2>
      <p class="mt-3 text-white/70">A fully hosted reset in nature—no hidden upsells.</p>
    </div>

    <!-- mobile: 1 col → 2 col → desktop: 3 col; tighter gaps on small -->
    <div class="mt-8 sm:mt-10 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4 sm:gap-6">
      {#each items as i}
        <article class="overflow-hidden rounded-2xl border border-white/10 bg-white/5 shadow-lg">
          <!-- mobile: use aspect ratio; desktop: keep your fixed heights -->
          <figure class="relative w-full aspect-[4/3] sm:aspect-[3/2] md:aspect-auto h-auto md:h-56">
            <img
              src={i.src}
              alt={i.title}
              loading="lazy"
              decoding="async"
              class="h-full w-full object-cover"
            />
            <div class="pointer-events-none absolute inset-0 bg-gradient-to-t from-black/20 to-transparent"></div>
          </figure>
          <div class="p-5 sm:p-6">
            <h3 class="text-lg md:text-xl font-semibold">{i.title}</h3>
            <p class="mt-2 text-white/70">{i.desc}</p>
          </div>
        </article>
      {/each}
    </div>
  </div>
</section>
