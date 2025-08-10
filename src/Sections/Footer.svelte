<script lang="ts">
  import { Leaf, Facebook, Instagram, Twitter, Youtube } from 'lucide-svelte';
</script>

<footer class="bg-gray-900 text-white py-16">
  <div class="max-w-7xl mx-auto px-6">
    <div class="grid grid-cols-1 lg:grid-cols-4 gap-12">
      <!-- Brand Section -->
      <div class="lg:col-span-2">
        <div class="flex items-center space-x-3 mb-6">
          <div class="w-12 h-12 bg-green-600 rounded-full flex items-center justify-center">
            <Leaf class="w-6 h-6 text-white" />
          </div>
          <div>
            <h3 class="text-2xl font-playfair font-bold tracking-wide">
              ROYAL OAK RETREAT
            </h3>
            <p class="text-sm text-gray-400 uppercase tracking-widest">Wellness Sanctuary</p>
          </div>
        </div>
        <p class="text-gray-300 font-inter leading-relaxed max-w-md">
          Nestled in Virginia's Blue Ridge Mountains, Royal Oak Retreat offers a transformative 
          wellness experience where luxury meets nature's healing power.
        </p>

        <!-- Social Links -->
        <div class="flex space-x-4 mt-8">
          <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-green-600 transition-colors duration-300">
            <Facebook class="w-5 h-5" />
          </a>
          <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-green-600 transition-colors duration-300">
            <Instagram class="w-5 h-5" />
          </a>
          <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-green-600 transition-colors duration-300">
            <Twitter class="w-5 h-5" />
          </a>
          <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-green-600 transition-colors duration-300">
            <Youtube class="w-5 h-5" />
          </a>
        </div>
      </div>

      <!-- Quick Links -->
      <div>
        <h4 class="text-lg font-playfair font-semibold mb-6">Quick Links</h4>
        <ul class="space-y-3 font-inter">
          <li><a href="#about" class="text-gray-300 hover:text-green-400 transition-colors duration-300">About Us</a></li>
          <li><a href="#amenities" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Amenities</a></li>
          <li><a href="#experiences" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Experiences</a></li>
          <li><a href="#booking" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Book Now</a></li>
          <li><a href="#contact" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Contact</a></li>
        </ul>
      </div>

      <!-- Wellness Programs -->
      <div>
        <h4 class="text-lg font-playfair font-semibold mb-6">Wellness Programs</h4>
        <ul class="space-y-3 font-inter">
          <li><a href="#" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Detox Retreats</a></li>
          <li><a href="#" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Meditation Sessions</a></li>
          <li><a href="#" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Sauna Therapy</a></li>
          <li><a href="#" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Cold Plunge</a></li>
          <li><a href="#" class="text-gray-300 hover:text-green-400 transition-colors duration-300">Forest Bathing</a></li>
        </ul>
      </div>
    </div>

    <!-- Bottom Section -->
    <div class="border-t border-gray-800 mt-12 pt-8">
      <div class="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
        <p class="text-gray-400 font-inter text-sm">
          © 2024 Royal Oak Retreat. All rights reserved.
        </p>
        <div class="flex space-x-6 font-inter text-sm">
          <a href="#" class="text-gray-400 hover:text-green-400 transition-colors duration-300">Privacy Policy</a>
          <a href="#" class="text-gray-400 hover:text-green-400 transition-colors duration-300">Terms of Service</a>
          <a href="#" class="text-gray-400 hover:text-green-400 transition-colors duration-300">Cancellation Policy</a>
        </div>
      </div>
    </div>
  </div>
</footer>
