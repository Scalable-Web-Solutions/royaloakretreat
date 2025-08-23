<script lang="ts">
  export let id = '';
  const faqs = [
    { q: 'Do I have to buy anything?', a: 'No purchase necessary. See Official Rules.' },
    { q: 'Is travel included?', a: 'Specify yes/no here. If not, include typical costs or shuttle info.' },
    { q: 'Who can enter?', a: 'Eligibility by age/country. Void where prohibited.' },
    { q: 'When do entries close?', a: 'Set your exact date/time & timezone.' }
  ];
</script>

<section {id} class="w-full py-12 sm:py-16 md:py-20">
  <h2 class="text-center font-serif text-3xl sm:text-4xl md:text-5xl">FAQ</h2>

  <div class="mx-auto mt-6 sm:mt-8 max-w-2xl sm:max-w-3xl rounded-2xl border border-white/10 bg-white/5 divide-y divide-white/10">
    {#each faqs as f, i}
      <details class="group p-4 sm:p-6" open={i === 0}>
        <summary class="flex items-center justify-between gap-3 cursor-pointer marker:hidden text-base sm:text-lg font-medium">
          {f.q}
          <!-- chevron -->
          <svg class="h-5 w-5 shrink-0 text-white/60 transition-transform group-open:rotate-180" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M5.23 7.21a.75.75 0 011.06.02L10 10.17l3.71-2.94a.75.75 0 111.04 1.08l-4.24 3.36a.75.75 0 01-.94 0L5.21 8.31a.75.75 0 01.02-1.1z" clip-rule="evenodd" />
          </svg>
        </summary>
        <p class="mt-2 text-sm sm:text-base text-white/70">{f.a}</p>
      </details>
    {/each}
  </div>

  <p class="mt-4 sm:mt-6 text-center text-xs sm:text-sm text-white/60">
    See <a class="underline" href="/rules">Official Rules</a> for full details.
  </p>
</section>
