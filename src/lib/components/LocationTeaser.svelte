<script lang="ts">
  export let id = '';
</script>

<section {id} class="relative border-y border-white/10 h-screen flex justify-center items-center bg-[url('https://encrypted-tbn3.gstatic.com/licensed-image?q=tbn:ANd9GcQ2dtW5NCeU11hOCJZ19w9Bxhmkuv2rsIyuEkO5P6y6NTHxc6_wKrk1OHkb9W3H5JKYeeYoDXmDxYufK_apRp18hJRSyAYrN2VZs24JIA')] bg-no-repeat bg-cover">
  <div class="absolute h-screen top-0 bg-gradient-to-t from-[#121313] to-transparent"></div>

  <div class="backdrop-blur-xl h-[102%] w-full flex justify-center items-center">
    <div class="mx-auto max-w-7xl px-6 py-20 grid md:grid-cols-2 gap-10 items-center">
    <div>
      <h2 class="text-3xl md:text-5xl font-serif">Close, but feels far away</h2>
      <p class="mt-4 text-white/70">~2 hours from Washington, DC. Limited shuttle seats available.</p>
      <button on:click={() => {
        window.location.href = '/#about';
      }} class="mt-4 bg-white shadow-lg text-black px-6 py-3 rounded-full w-full">View Getaway Process</button>

    </div>
    <img src="https://static.wixstatic.com/media/1c989e_67c3d45027e344dabda77834c04f55ce~mv2.png/v1/fill/w_1562,h_1154,al_c,q_90,enc_avif,quality_auto/1c989e_67c3d45027e344dabda77834c04f55ce~mv2.png" alt="Retreat Location" class="w-full h-80 rounded-3xl border border-white/10 shadow-xl">

  </div>
  </div>
</section>
