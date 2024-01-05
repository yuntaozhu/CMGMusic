<!-- InitialSection.svelte -->
<script>
  // Importing Svelte transition modules
  import { slide, fade } from 'svelte/transition';

  // Array of gallery items with image URLs and descriptions
  const gallery_items = [
    { url: "assets/CMG-DEVS1.jpg", description: "CMG group photo" },
    { url: "assets/CMG-DEVS2.png", description: "CMG group photo" },
    { url: "assets/CMG-DEVS3.jpg", description: "CMG group photo" },
    { url: "assets/CMG-DEVS4.jpg", description: "CMG group photo" },
  ];

  // Current slide item index for the slideshow
  let currentSlideItem = 0;

  // Function to transition to the next image in the slideshow
  function nextImage() {
    currentSlideItem = (currentSlideItem + 1) % gallery_items.length;
  }

  // Automatically change the image every 3 seconds
  let interval;

  function startAutoSlide() {
    interval = setInterval(nextImage, 3000);
  }

  startAutoSlide(); // Start the automatic slideshow

  // Function to handle smooth scrolling to a section
  function scrollToSection(sectionId) {
    const targetSection = document.getElementById(sectionId);
    if (targetSection) {
      const offset = targetSection.offsetTop - 75; // Adjust the offset as needed
      window.scrollTo({
        top: offset,
        behavior: 'smooth',
      });
    }
  }
</script>

<section class="container mx-auto relative pt-8 pb-[130px]">
  <div class="flex flex-col min-h-[85vh] pt-10 gap-10 md:flex-row md:align-center md:justify-evenly md:gap-10 2xl:gap-2">

    <!-- Left side: Slideshow with Fade Animation -->
    <div class="relative flex flex-row mx-auto my-auto ss:text-right ss:justify-end">
      <div class="absolute flex right-[-25px] top-[-40px] md:right-[-45px]">
        <img src="Hexagon Gradient.svg" alt="Hexagon" class="max-w-[100%] w-16 md:w-24"/>
      </div>

      <div class="absolute bottom-[-40px] left-[-25px] md:left-[-45px]">
        <img src="Hexagon Gradient.svg" alt="Hexagon" class="max-w-[100%] w-16 md:w-24"/>
      </div>

      <div class="slideshow ss:pt-0 md:pt-0 flex justify-center items-center md:flex-1 3xl:max-w-screen-sm w-[300px] h-[350px]">
        <!-- Slideshow images loop -->
        {#each [gallery_items[currentSlideItem]] as item (currentSlideItem)}
          <img in:slide out:fade src={item.url} alt={item.description} class="w-full h-full object-cover rounded-2xl ax-w-xs 2xl:max-w-sm 3xl:max-w-lg m-auto"/>
        {/each}
      </div>

      <div class="absolute top-[20px] right-[-15px] md:top-[40px] md:right-[-30px]">
        <img src="Hexagon Gradient.svg" alt="Hexagon" class="max-w-[100%] w-8 md:w-16"/>
      </div>

      <div class="absolute bottom-[20px] left-[-15px] md:bottom-[40px] md:left-[-30px]">
        <img src="Hexagon Gradient.svg" alt="Hexagon" class="max-w-[100%] w-8 md:w-16"/>
      </div>
    </div>

    <!-- Right side: Text and scroll icon -->
    <div class="flex flex-col md:justify-center md:flex-1 gap-6 md:max-w-xl 3xl:max-w-2xl top-[-50px] ss:text-left">
      <div class="flex flex-col gap-3">

        <!-- "Meet the Team" text -->
        <h1 class="text-4xl font-bold leading-tight lg:text-5xl md:leading-snug tracking-wide text-center">
          Meet the Team
        </h1>

        <!-- Description text -->
        <p class="font-light text-slate-200 text-sm 3xl:text-base 3xl:max-w-xl text-justify">
          Unveiling the Brilliant Minds and Creative Geniuses Who Drive the Vision and Success of Alliance of Computer Science Students - UPLB
        </p>

        <div class="flex justify-center items-center space-x-4">
          <!-- Button to view members section with smooth scroll -->
          <button
            class="text-xs ss:text-base bg-gradient-to-r from-blue-700 to-blue-500 text-white px-4 py-2 rounded-2xl hover:from-blue-500 hover:scale-105 hover:shadow-md transition duration-300 ease-in-out"
            on:click={() => scrollToSection('executives')}
          >
            View Members
          </button>

          <!-- Button to view roster section with smooth scroll -->
          <button
            class="text-xs ss:text-base bg-transparent border-2 border-gradient-to-r from-blue-700 to-blue-500 text-white px-4 py-2 rounded-2xl hover:shadow-md hover:scale-105 transition duration-300 ease-in-out"
            on:click={() => scrollToSection('member-roster')}
          >
            View Roster
          </button>
        </div>

      </div>
    </div>
  </div>

  <!-- Scroll icon for large screens -->
  <div class="w-8 h-10 border-2 rounded-full m-auto pt-2 mt-6 sm:mt-0 mb-10 hidden md:block">
    <div class="w-1 h-3 bg-white rounded-md animate-bounce m-auto" />
  </div>
</section>

<style>
  /* Styling for the slideshow */
  .slideshow {
    filter: drop-shadow(0px 4px 4px #000000);
    border-radius: 16px;
    border: 0.01rem solid rgba(255, 255, 255, 0.1);
    background: linear-gradient(
      135deg,
      rgba(255, 255, 255, 0) 0%,
      rgba(255, 255, 255, 0.2) 100%
    );
  }
</style>
