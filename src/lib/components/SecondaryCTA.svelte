<script lang="ts">
  export let id = '';
</script>

<section {id} class="w-full sm:py-5 md:py-2 text-center">
  <div class="mx-auto max-w-3xl rounded-3xl border border-white/10 bg-white/5 p-6 sm:p-8">
    <h2 class="font-serif text-2xl sm:text-3xl md:text-4xl">Last chance... entries close soon</h2>
    <p class="mt-2 text-sm sm:text-base text-white/70">It takes 10 seconds. Unsubscribe anytime.</p>

    <form class="mt-4 sm:mt-6 grid grid-cols-1 md:grid-cols-3 gap-3 sm:gap-4" on:submit|preventDefault={() => { /* submit */ }}>
      <input
        required
        placeholder="Your name"
        class="rounded-xl bg-black/30 border border-white/10 px-4 py-3 sm:py-3.5 outline-none focus:ring-2 focus:ring-white/30"
      />
      <input
        required
        type="email"
        placeholder="your@email.com"
        class="rounded-xl bg-black/30 border border-white/10 px-4 py-3 sm:py-3.5 outline-none focus:ring-2 focus:ring-white/30"
      />
      <button class="rounded-xl px-4 py-3.5 md:py-3 bg-white text-black font-semibold hover:opacity-90">
        Enter Giveaway
      </button>
    </form>

    <p class="mt-3 text-xs sm:text-sm text-white/50">
      By entering you agree to our <a class="underline" href="/rules">Rules</a> & <a class="underline" href="/privacy">Privacy Policy</a>.
    </p>
  </div>
</section>
