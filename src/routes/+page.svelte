<script lang="ts">
  import Navbar from '$lib/components/Navigation.svelte';
  import Hero from '$lib/components/Hero.svelte';

  import WhatYouWin from '$lib/components/WhatYouWin.svelte';
  import HowItWorks from '$lib/components/HowItWorks.svelte';
  import SocialProof from '$lib/components/SocialProof.svelte';
  import Protocols from '$lib/components/Protocols.svelte';
  import AboutRetreat from '$lib/components/AboutRetreat.svelte';
  import FAQ from '$lib/components/FAQ.svelte';

  import SecondaryCTA from '$lib/components/SecondaryCTA.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<div class="h-screen overflow-y-auto bg-gradient-to-b from-[#0b0b0b] to-[#111] text-white">

  <!-- PAGE 1 -->
  <section class="min-h-screen">
    <Navbar />
    <Hero />
  </section>

  <!-- PAGE 2 -->
  <section id="prize" class=" min-h-screen">
    <WhatYouWin />
  </section>

  <!-- PAGE 5 -->
  <section id="about" class="min-h-screen">
    <AboutRetreat />
  </section>

    <!-- PAGE 4 -->
  <section id="how" class="min-h-screen">
    <HowItWorks />
  </section>

  <!-- PAGE 6 -->
  <section id="faq" class="snap-start min-h-screen flex flex-col justify-center">
  <div class="mx-auto w-full max-w-7xl px-4 sm:px-6">
    <FAQ />
    <div class="mt-0">
      <SecondaryCTA id="enter-bottom" />
    </div>
  </div>
</section>

  <section class="snap-end">
     <Footer />
  </section>
</div>

