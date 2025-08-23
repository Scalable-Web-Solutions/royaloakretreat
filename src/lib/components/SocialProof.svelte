<script lang="ts">
  export let id = '';
  const items = [
    {name: 'Leah S.', text: 'Most peaceful 3 days of my year. 10/10.'},
    {name: 'Jordan M.', text: 'Breathwork and sauna changed everything.'},
    {name: 'Arman T.', text: 'Staff were incredible—thoughtful and professional.'}
  ];
</script>

<section {id} class="mx-auto max-w-7xl px-6 py-20">
  <h2 class="text-3xl md:text-5xl font-serif text-center">Guest Reviews</h2>
  <div class="mt-10 grid gap-6 md:grid-cols-3">
    {#each items as r}
      <blockquote class="rounded-2xl bg-white/5 p-6 border border-white/10">
        <p class="text-white/90">&ldquo;{r.text}&rdquo;</p>
        <footer class="mt-4 text-white/60">— {r.name}</footer>
      </blockquote>
    {/each}
  </div>
</section>
