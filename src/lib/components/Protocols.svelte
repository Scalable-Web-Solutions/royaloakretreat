<script lang="ts">
  export let id = '';
</script>

<section {id} class="bg-white/5 border-y border-white/10">
  <div class="mx-auto max-w-7xl px-6 py-20 grid md:grid-cols-2 gap-10">
    <div>
      <h2 class="text-3xl md:text-5xl font-serif">Safety & Protocols</h2>
      <p class="mt-4 text-white/70">Licensed staff. Hygienic facilities. Clear contraindications.</p>
      <ul class="mt-6 space-y-3 text-white/80 list-disc pl-5">
        <li>Daily sanitation of cedar tubs & saunas</li>
        <li>On-site first aid & emergency plan</li>
        <li>Intake form to honor medical needs</li>
        <li>Vegetarian/vegan/gluten-free options</li>
      </ul>
      <a href="/terms" class="mt-6 inline-block underline text-white/80">Read full protocols</a>
    </div>
    <div class="rounded-3xl bg-[url('/images/sauna.jpg')] bg-cover bg-center min-h-[320px]"></div>
  </div>
</section>
