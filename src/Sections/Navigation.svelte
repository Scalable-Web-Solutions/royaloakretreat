<script lang="ts">
  import { Leaf } from 'lucide-svelte';
</script>

<nav class="absolute top-0 left-0 right-0 z-50 px-6 py-4">
  <div class="max-w-7xl mx-auto flex items-center justify-between">
    <!-- Logo -->
    <div class="flex items-center space-x-3">
      <div class="w-12 h-12 bg-white/20 backdrop-blur-sm rounded-full flex items-center justify-center">
        <Leaf class="w-6 h-6 text-white" />
      </div>
      <div class="text-white">
        <h1 class="text-xl font-playfair font-semibold tracking-wide">
          ROYAL OAK
        </h1>
        <p class="text-xs uppercase tracking-widest opacity-90">RETREAT</p>
      </div>
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
