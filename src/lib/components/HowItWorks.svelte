<script lang="ts">
  import { Mail, CheckCircle2, Trophy } from 'lucide-svelte';
  export let id = '';
  export let drawDate = 'Sept 12 @ 12:00pm PST';

  const steps = [
    { n: 1, t: 'Enter', d: 'Name + Email. Takes 10 seconds.', Icon: Mail },
    { n: 2, t: 'Confirm', d: 'Click the link we email you.', Icon: CheckCircle2 },
    { n: 3, t: 'Announcement', d: `Winner announced ${drawDate}.`, Icon: Trophy }
  ];
</script>

<section {id} class="relative border-y border-white/10 bg-gradient-to-b from-white/[0.03] via-transparent to-white/[0.03] h-screen flex flex-col justify-center">
      <div class="pointer-events-none fixed -top-20 left-0 right-0 h-10
              bg-gradient-to-b from-[#0b0b0b]/70 to-transparent"></div>
  <div class="relative mx-auto max-w-7xl px-6 py-20">
    <h2 class="text-center font-serif text-3xl md:text-5xl">How It Works</h2>
    <div class="relative mt-12">
      <div class="hidden md:block absolute left-0 right-0 top-16 h-px bg-gradient-to-r from-transparent via-white/15 to-transparent"></div>

      <div class="grid gap-6 md:grid-cols-3">
        {#each steps as s}
          <article class="group relative rounded-2xl border border-white/10 bg-white/[0.06] backdrop-blur-xl p-6 shadow-[0_12px_40px_rgba(0,0,0,.25)]">
            <div class="flex items-center gap-4">
              <div class="grid h-12 w-12 place-items-center rounded-2xl bg-white/10 ring-1 ring-white/20">
                <s.Icon class="h-6 w-6 text-white/90" />
              </div>
              <h3 class="text-xl font-semibold">{s.t}</h3>
            </div>
            <p class="mt-3 leading-relaxed text-white/70">{s.d}</p>
          </article>
        {/each}
      </div>
      <div class="mt-12 text-center mx-auto w-[100%]">
        <button on:click={() => {
          window.location.href = '/#faq';
        }} class="border border-white/10 bg-white  shadow-lg text-black px-6 py-3 rounded-full w-full">Register Now</button>
      </div>

    </div>
  </div>
</section>
