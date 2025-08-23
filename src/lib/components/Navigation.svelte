<script lang="ts">
  import { Leaf } from 'lucide-svelte';

  let logo: string = 'https://static.wixstatic.com/media/1c989e_c1f6f4cd81194410957b71a08b31a3a9~mv2.png/v1/fill/w_574,h_472,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/Logo%20White.png'
</script>

<nav class="fixed top-0 left-0 right-0 z-50 px-6 py-4">
  <div class="max-w-6xl mx-auto flex items-center justify-between">
    <!-- Logo -->
    <div class="flex items-center space-x-3">
      <img src={logo} alt="Logo" class="w-20 h-17" />
    </div>

    <!-- Navigation Links -->
    <div class="hidden md:flex items-center space-x-8">
      <a href="#about" class="text-white/90 hover:text-white transition-colors duration-300 font-inter text-sm">
        About
      </a>
      <a href="#trust" class="text-white/90 hover:text-white transition-colors duration-300 font-inter text-sm">
        Trust
      </a>
      <a href="#protocols" class="text-white/90 hover:text-white transition-colors duration-300 font-inter text-sm">
        Protocols
      </a>
    </div>

    <!-- CTA Button -->
    <button class="bg-white/10 backdrop-blur-sm border border-white/20 text-white px-6 py-3 rounded-full hover:bg-white/20 transition-all duration-300 font-inter text-sm font-medium">
      Exclusive Offer
    </button>
  </div>
</nav>
