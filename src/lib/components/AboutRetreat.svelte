<script lang="ts">
  export let id = '';
</script>

<section
  {id}
  class="relative border-y border-white/10 bg-gradient-to-b from-white/[0.02] via-transparent to-white/[0.02] min-h-screen"
>
  <div class="mx-auto max-w-7xl px-4 sm:px-6 py-12 sm:py-16 md:py-20">
    <div class="grid items-start gap-10 md:grid-cols-2">

      <!-- COMP 1: LOCATION (left, top) -->
      <div>
        <h2 class="text-3xl md:text-5xl font-serif">Close, but feels far away</h2>
        <p class="mt-4 text-white/70">~2 hours from Washington, DC. Limited shuttle seats available.</p>
        <button
          on:click={() => { window.location.href = '/#about'; }}
          class="mt-4 w-full rounded-full bg-white px-6 py-3 text-black shadow-lg hover:opacity-90"
        >
          View Getaway Process
        </button>

        <img
          src="https://static.wixstatic.com/media/1c989e_67c3d45027e344dabda77834c04f55ce~mv2.png/v1/fill/w_1562,h_1154,al_c,q_90,enc_avif,quality_auto/1c989e_67c3d45027e344dabda77834c04f55ce~mv2.png"
          alt="Retreat location"
          class="mt-6 h-80 w-full rounded-2xl object-cover shadow-xl"
        />
      </div>

      <!-- COMP 2: ABOUT (right, staggered down) -->
      <div class="md:mt-14"> <!-- adjust mt for more/less stagger: md:mt-10..md:mt-24 -->
        <img
          src="https://static.wixstatic.com/media/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png/v1/fill/w_1450,h_1120,al_c,q_90,enc_avif,quality_auto/3cf872_e64e6f7eab39495ca1384d02554bfa7f~mv2.png"
          alt="Royal Oak retreat grounds"
          loading="lazy"
          decoding="async"
          class="h-[320px] w-full rounded-2xl object-cover shadow-xl md:h-[460px]"
        />

        <div class="mt-6 max-w-xl">
          <span class="text-xs tracking-widest uppercase text-white/50">About</span>
          <h3 class="mt-2 text-3xl md:text-5xl font-serif">About Royal Oak</h3>
          <p class="mt-4 text-white/70">
            Hidden among old-growth pines, Royal Oak is a small-format wellness retreat focused on nervous
            system reset through heat, cold, breathwork, and slow food.
          </p>
          <p class="mt-3 text-white/70">
            We host fewer than 12 guests at a time to maintain silence, space, and care.
          </p>

          <!-- simple chips without glass -->
          <div class="mt-6 grid grid-cols-3 gap-4">
            <div class="rounded-xl bg-white/[0.06] p-4 text-center">
              <div class="text-2xl font-semibold">≤12</div>
              <div class="text-xs text-white/70">Guests max</div>
            </div>
            <div class="rounded-xl bg-white/[0.06] p-4 text-center">
              <div class="text-2xl font-semibold">Daily</div>
              <div class="text-xs text-white/70">Sauna • Cold</div>
            </div>
            <div class="rounded-xl bg-white/[0.06] p-4 text-center">
              <div class="text-2xl font-semibold">Chef</div>
              <div class="text-xs text-white/70">Slow food</div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>
