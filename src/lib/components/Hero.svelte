<script lang="ts">
  import { ChevronDown } from 'lucide-svelte';
  import videoSrc from '$lib/assets/royaloak.mp4';

  let logo: string = 'https://static.wixstatic.com/media/1c989e_c1f6f4cd81194410957b71a08b31a3a9~mv2.png/v1/fill/w_574,h_472,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/Logo%20White.png'

  let formData = { name: '', email: '' };
  let isVideoPlaying = true;

  function handleInputChange(e: Event) {
    const target = e.target as HTMLInputElement;
    formData = { ...formData, [target.name]: target.value };
  }

  function handleSubmit(e: Event) {
    e.preventDefault();
    console.log('Form submitted:', formData);
    // Handle form submission logic here
  }
</script>

<section class="relative min-h-screen overflow-hidden">
  <!-- Video Background -->
  <div class="absolute inset-0">
    <video
      class="w-full h-full object-cover filter blur-sm scale-105"
      src={videoSrc}
      autoplay
      muted
      loop
      playsinline
    >
      <source src={videoSrc} type="video/mp4" />
    </video>
    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/30 to-transparent"></div>
    <div class="absolute inset-0 bg-black/20"></div>
  </div>

  <!-- Hero Content -->
  <div class="relative z-10 min-h-screen flex items-center">
    <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-5 items-center">
      <!-- Left Column - Content Form -->
      <div class="bg-white/10 backdrop-blur-lg rounded-3xl p-8 lg:p-12 border border-white/20">
        <!-- Logo Section -->
        <div class="text-center mb-8">
          <div class="inline-flex flex-col items-center">
            <div class="text-white mb-4">
              <img src={logo} alt="Logo" class="w-40 h-32" />

            </div>
          </div>
        </div>

        <!-- Tagline -->
        <div class="text-center mb-8">
          <h2 class="text-white text-2xl lg:text-3xl font-playfair font-medium leading-relaxed mb-4">
            Escape the noise. Detox your body.
            <br />
            Reconnect with yourself.
          </h2>
          <p class="text-white/80 text-lg font-inter leading-relaxed">
            Sign up with your email to follow
            <br />
            along with progress
          </p>
        </div>

        <!-- Form -->
        <form on:submit={handleSubmit} class="space-y-4">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div>
              <label class="text-white text-sm font-inter mb-2 block">Name *</label>
              <input
                type="text"
                name="name"
                bind:value={formData.name}
                on:input={handleInputChange}
                class="w-full px-4 py-3 bg-white/20 backdrop-blur-sm border border-white/30 rounded-lg text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-white/50 transition-all duration-300"
                placeholder="Your name"
                required
              />
            </div>
            <div>
              <label class="text-white text-sm font-inter mb-2 block">Email *</label>
              <input
                type="email"
                name="email"
                bind:value={formData.email}
                on:input={handleInputChange}
                class="w-full px-4 py-3 bg-white/20 backdrop-blur-sm border border-white/30 rounded-lg text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-white/50 transition-all duration-300"
                placeholder="your@email.com"
                required
              />
            </div>
          </div>
          <button
            type="submit"
            class="w-full bg-white text-gray-800 py-4 rounded-lg font-inter font-medium hover:bg-white/90 transition-all duration-300 shadow-lg"
          >
            Enter Free Getaway Giveaway
          </button>
        </form>
      </div>

      <!-- Right Column - Modern Cabin Preview -->
      <div class="hidden lg:block">
        <div class="relative flex gap-5">
          <img 
            src="https://static.wixstatic.com/media/1c989e_7277198225eb4c459d3bc7fd6f294ac0~mv2.png/v1/fill/w_600,h_1108,al_c,q_90,usm_0.66_1.00_0.01,enc_avif,quality_auto/rear%20cold%20plunge%202.png"
            alt="Modern retreat cabin in forest"
            class="rounded-2xl shadow-2xl object-contain h-[620px]"


          />
          <img 
            src="https://static.wixstatic.com/media/1c989e_b2d698c12b9d41a09f867cd389aaadb3~mv2.png/v1/fill/w_300,h_554,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/Sundress%20Lounger%202.png"
            alt="Modern retreat cabin in forest"
            class="rounded-2xl shadow-2xl object-contain h-[620px]"


          />
        </div>
      </div>
    </div>
  </div>

  <!-- Scroll Indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 z-20">
    <ChevronDown class="w-6 h-6 text-white animate-bounce" />
  </div>
</section>
