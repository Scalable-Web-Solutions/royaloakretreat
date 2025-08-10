<script lang="ts">
  import { Droplets, TreePine, Flame, Snowflake } from 'lucide-svelte';

  const amenities = [
    {
      icon: TreePine,
      title: "Forest Immersion",
      description: "Guided nature walks and meditation sessions deep in the Virginia wilderness."
    },
    {
      icon: Flame,
      title: "Private Sauna Sessions",
      description: "Traditional Finnish saunas with aromatic wood and therapeutic heat treatments."
    },
    {
      icon: Snowflake,
      title: "Cold Plunge Therapy",
      description: "Invigorating cold water immersion for enhanced recovery and mental clarity."
    },
    {
      icon: Droplets,
      title: "Natural Spring Waters",
      description: "Pure mountain spring water for hydration and therapeutic soaks."
    }
  ];
</script>

<section class="py-20 bg-gradient-to-br from-green-900 via-green-800 to-green-700 relative overflow-hidden">
  <!-- Background Pattern -->
  <div class="absolute inset-0 opacity-10 pointer-events-none select-none">
    <div class="absolute top-10 left-10 w-64 h-64 border border-white rounded-full"></div>
    <div class="absolute bottom-10 right-10 w-96 h-96 border border-white rounded-full"></div>
    <div class="absolute top-1/2 left-1/3 w-32 h-32 border border-white rounded-full"></div>
  </div>

  <div class="relative z-10 max-w-7xl mx-auto px-6">
    <!-- Section Header -->
    <div class="text-center mb-16">
      <h2 class="text-4xl lg:text-5xl font-playfair font-bold text-white mb-6">
        Wellness Amenities
      </h2>
      <p class="text-green-100 text-lg font-inter max-w-3xl mx-auto leading-relaxed">
        Immerse yourself in carefully curated experiences designed to restore your body, 
        mind, and spirit through the healing power of nature.
      </p>
    </div>

    <!-- Amenities Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
      {#each amenities as amenity}
        <div 
          class="group bg-white/10 backdrop-blur-sm border border-white/20 rounded-2xl p-8 hover:bg-white/15 transition-all duration-300 transform hover:-translate-y-2"
        >
          <div class="w-16 h-16 bg-white/20 rounded-xl flex items-center justify-center mb-6 group-hover:bg-white/30 transition-all duration-300">
            <svelte:component this={amenity.icon} class="w-8 h-8 text-white" />
          </div>
          
          <h3 class="text-white text-xl font-playfair font-semibold mb-4">
            {amenity.title}
          </h3>
          
          <p class="text-green-100 font-inter leading-relaxed">
            {amenity.description}
          </p>
        </div>
      {/each}
    </div>

    <!-- CTA Section -->
    <div class="text-center mt-16">
      <button class="bg-white text-green-800 px-8 py-4 rounded-full font-inter font-semibold text-lg hover:bg-green-50 transition-all duration-300 shadow-lg transform hover:scale-105">
        Book Your Retreat Experience
      </button>
    </div>
  </div>
</section>