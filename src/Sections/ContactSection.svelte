<script lang="ts">
  import { MapPin, Phone, Mail, Clock } from 'lucide-svelte';

  let formData = {
    name: '',
    email: '',
    phone: '',
    message: ''
  };

  function handleInputChange(event: Event) {
    const target = event.target as HTMLInputElement | HTMLTextAreaElement;
    formData = { ...formData, [target.name]: target.value };
  }

  function handleSubmit(event: Event) {
    event.preventDefault();
    console.log('Contact form submitted:', formData);
    // You could add success feedback or send the form data here
  }
</script>

<section class="py-20 bg-gradient-to-br from-green-50 to-emerald-50">
  <div class="max-w-7xl mx-auto px-6">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
      <!-- Contact Information -->
      <div>
        <h2 class="text-4xl lg:text-5xl font-playfair font-bold text-gray-800 mb-8">
          Plan Your Retreat
        </h2>
        <p class="text-gray-600 text-lg font-inter leading-relaxed mb-12">
          Ready to escape to nature's embrace? Contact us to customize your perfect wellness retreat experience.
        </p>

        <div class="space-y-8">
          <div class="flex items-start space-x-4">
            <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center flex-shrink-0">
              <MapPin class="w-6 h-6 text-green-600" />
            </div>
            <div>
              <h3 class="font-playfair font-semibold text-gray-800 text-lg mb-2">Location</h3>
              <p class="text-gray-600 font-inter">
                Blue Ridge Mountains<br />
                Shenandoah Valley, Virginia
              </p>
            </div>
          </div>

          <div class="flex items-start space-x-4">
            <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center flex-shrink-0">
              <Phone class="w-6 h-6 text-green-600" />
            </div>
            <div>
              <h3 class="font-playfair font-semibold text-gray-800 text-lg mb-2">Phone</h3>
              <p class="text-gray-600 font-inter">(540) 555-RETREAT</p>
            </div>
          </div>

          <div class="flex items-start space-x-4">
            <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center flex-shrink-0">
              <Mail class="w-6 h-6 text-green-600" />
            </div>
            <div>
              <h3 class="font-playfair font-semibold text-gray-800 text-lg mb-2">Email</h3>
              <p class="text-gray-600 font-inter">hello@royaloakretreat.com</p>
            </div>
          </div>

          <div class="flex items-start space-x-4">
            <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center flex-shrink-0">
              <Clock class="w-6 h-6 text-green-600" />
            </div>
            <div>
              <h3 class="font-playfair font-semibold text-gray-800 text-lg mb-2">Availability</h3>
              <p class="text-gray-600 font-inter">
                Daily: 8:00 AM - 6:00 PM<br />
                Weekends & Holidays Available
              </p>
            </div>
          </div>
        </div>
      </div>

      <!-- Contact Form -->
      <div class="bg-white rounded-3xl p-8 shadow-lg">
        <h3 class="text-2xl font-playfair font-bold text-gray-800 mb-6">
          Send Us a Message
        </h3>
        
        <form on:submit={handleSubmit} class="space-y-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div>
              <label class="block text-gray-700 font-inter font-medium mb-2">
                Full Name *
              </label>
              <input
                type="text"
                name="name"
                bind:value={formData.name}
                on:input={handleInputChange}
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-green-500 transition-colors duration-300"
                placeholder="Your name"
                required
              />
            </div>
            
            <div>
              <label class="block text-gray-700 font-inter font-medium mb-2">
                Email *
              </label>
              <input
                type="email"
                name="email"
                bind:value={formData.email}
                on:input={handleInputChange}
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-green-500 transition-colors duration-300"
                placeholder="your@email.com"
                required
              />
            </div>
          </div>

          <div>
            <label class="block text-gray-700 font-inter font-medium mb-2">
              Phone Number
            </label>
            <input
              type="tel"
              name="phone"
              bind:value={formData.phone}
              on:input={handleInputChange}
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-green-500 transition-colors duration-300"
              placeholder="(555) 123-4567"
            />
          </div>

          <div>
            <label class="block text-gray-700 font-inter font-medium mb-2">
              Message *
            </label>
            <textarea
              name="message"
              bind:value={formData.message}
              on:input={handleInputChange}
              rows={4}
              class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-green-500 transition-colors duration-300 resize-none"
              placeholder="Tell us about your ideal retreat experience..."
              required
            ></textarea>
          </div>

          <button
            type="submit"
            class="w-full bg-green-600 text-white py-4 rounded-lg font-inter font-semibold text-lg hover:bg-green-700 transition-colors duration-300 shadow-lg"
          >
            Send Message
          </button>
        </form>
      </div>
    </div>
  </div>
</section>
