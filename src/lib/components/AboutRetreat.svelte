<script lang="ts">
  export let id = '';
</script>

<section {id} class="relative border-y border-white/10 bg-gradient-to-b from-white/[0.03] via-transparent to-white/[0.03] h-screen flex">
  <div class="mx-auto max-w-7xl px-6 py-20 grid items-center gap-10 md:grid-cols-2 mt-30">

    <!-- IMAGE CARD -->
    <figure class="group relative overflow-hidden rounded-3xl border border-white/10 bg-white/5 backdrop-blur-sm shadow-[0_20px_60px_rgba(0,0,0,.35)]">
      <img
        src="https://static.wixstatic.com/media/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png/v1/fill/w_1450,h_1120,al_c,q_90,enc_avif,quality_auto/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png"
        alt="Royal Oak retreat grounds"
        loading="lazy"
        decoding="async"
        class="h-[360px] w-full object-cover md:h-[520px] transition-transform duration-500 group-hover:scale-[1.03]"
      />
      <div class="pointer-events-none absolute inset-0 bg-gradient-to-t from-black/25 to-transparent"></div>
    </figure>

    <!-- COPY -->
    <div class="max-w-xl mt-30">
      <span class="text-xs tracking-widest uppercase text-transparent">About</span>
      <h2 class="mt-2 text-3xl md:text-5xl font-serif">About Royal Oak</h2>

      <p class="mt-4 text-white/70">
        Hidden among old-growth pines, Royal Oak is a small-format wellness retreat
        focused on nervous system reset through heat, cold, breathwork, and slow food.
      </p>
      <p class="mt-3 text-white/70">
        We host fewer than 12 guests at a time to maintain silence, space, and care.
      </p>

      <!-- SMALL FACT CHIPS (optional, looks premium & consistent) -->
      <div class="mt-8 grid grid-cols-3 gap-4">
        <div class="rounded-2xl border border-white/10 bg-white/5 p-4 text-center">
          <div class="text-2xl font-semibold">≤12</div>
          <div class="text-xs text-white/60">Guests max</div>
        </div>
        <div class="rounded-2xl border border-white/10 bg-white/5 p-4 text-center">
          <div class="text-2xl font-semibold">Daily</div>
          <div class="text-xs text-white/60">Sauna • Cold</div>
        </div>
        <div class="rounded-2xl border border-white/10 bg-white/5 p-4 text-center">
          <div class="text-2xl font-semibold">Chef</div>
          <div class="text-xs text-white/60">Slow food</div>
        </div>
      </div>
    </div>
  </div>
</section>
