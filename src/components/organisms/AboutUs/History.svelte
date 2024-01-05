<script>
  // import SplideJS for the Dev Story Carousel
  import { Splide, SplideSlide, SplideTrack } from "@splidejs/svelte-splide";
  import "@splidejs/svelte-splide/css";

  // Splide Options to autoplay
  const options = {
    rewind: true,
    gap: "1rem",
    autoplay: true,
    arrows: false, // show left and right arrows
    interval: 3000,
    speed: 1000,
    pagination: false,
    type: "fade",
  };
</script>

<div
  class="flex justify-center items-center pt-20 h-fit lg:h-screen xl:h-screen"
>
  <div class="flex flex-col gap-8 p-16 w-100 md:p-16 lg:p-16 lg:w-2/3 xl:w-2/3">
    <div class="relative z-0">
      <Splide {options} hasTrack={false} aria-label="...">
        <div class="custom-wrapper">
          <SplideTrack>
            <SplideSlide>
              <img src="/assets/DiscoverCMG.png" alt="photo" />
            </SplideSlide>
            <SplideSlide>
              <img src="/assets/DiscoverCMG.png" alt="photo" />
            </SplideSlide>
            <SplideSlide>
              <img src="/assets/DiscoverCMG.png" alt="photo" />
            </SplideSlide>
            <SplideSlide>
              <img src="/assets/DiscoverCMG.png" alt="photo" />
            </SplideSlide>
          </SplideTrack>

          <div class="splide__arrows" />
        </div>
      </Splide>
    </div>

    <div class="text-justify w-100">
      <div
        class="text-container flex flex-col gap-5 justify-center items-center w-100"
      >
        <p class="text-lg font-extralight">
          Established in December of 2014, The <span
            style="color:var(--color-sky-blue)"
            >Alliance of Computer Science - UPLB</span
          > is an academic student organization that aims to assist the university
          by developing and upholding the value of service and discipline, as well
          as honor and excellence as “Iskolar ng Bayan para sa Bayan” among its members.
        </p>
      </div>
    </div>
    <div
      class="hidden md:flex w-8 h-10 border-2 rounded-full m-auto pt-2 mt-6 sm:mt-0 mb-10"
    >
      <div class="w-1 h-3 bg-white rounded-md animate-bounce m-auto" />
    </div>
  </div>
</div>

<!-- <div class="p-5 absolute z-0">
          <Splide {options} hasTrack={false} aria-label="...">
            <div class="custom-wrapper">
              <SplideTrack>
                {#each photos as photo}
                  <SplideSlide>
                    <img src={photo} alt="photo" />
                  </SplideSlide>
                {/each}
              </SplideTrack>

              <div class="splide__arrows" />
            </div>
          </Splide>
        </div> -->

<!-- <div
  class="pl-10 pr-10 pt-10 lg:pl-20 xl:pl-20 lg:pr-20 xl:pr-20 mt-12 xl:h-screen"
>
  <img src="/assets/aboutus-photo.jpg" alt="photo" class="shadow-2xl" />
</div> -->

<!-- <div
        class="relative z-10 flex items-center justify-center glassmorphic-box border-l pl-8 pr-8 pt-2 pb-2"
      >
        <p class="history-title text-3xl text-left">Who are we?</p>
      </div> -->

<style>
  /* @media (min-width: 1100px) and (max-width: 1330px) {
    .text-container {
      padding-top: 0px;
      padding: 10rem;
    }

    .photo-container {
      padding: 15rem;
      padding-top: 2rem;
    }
  }

  @media (min-width: 1100px) and (max-width: 1280px) {
    .text-container {
      margin-top: 9rem;
      padding: 2rem;
    }

    .photo-container {
      padding: 14rem;
      padding-top: 2rem;
    }
  } */
  .history-title {
    transition: color 0.5s, text-shadow 0.5s;
  }

  .history-container:hover .history-title {
    text-shadow: 0 0 1px white, 0 0 3px white, 0 0 3px white;
    color: transparent;
  }

  .glassmorphic-box {
    width: fit-content;
    height: fit-content;
    flex-shrink: 0;
    border-radius: 16px;
    border: 0.01rem solid rgba(255, 255, 255, 0.1);
    background: linear-gradient(
      135deg,
      rgba(255, 255, 255, 0.2) 0%,
      rgba(255, 255, 255, 0) 100%
    );
    backdrop-filter: blur(21px);
  }
</style>
