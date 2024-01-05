<script lang="ts">
  // DevStoriesHeader and DevStoriesTemplate located in the molecules folder
  import { DevStoriesHeader, DevStoriesTemplate } from "$components";
  // devStories is an object that contains the name, position, story, and image url of each developer
  let devStories = {
    "Cuarteto Latinoamericano ": [
      "formed in 1982, known worldwide as the leading proponent of Latin American music for string quartet. ",
      "This Latin Grammy winning ensemble from Mexico, Bitran brothers, violinists Saul and Aron and cellist Alvaro, along with violist Javier Montiel. Together they have recorded most of the Latin American repertoire for string quartet. The sixth volume of their Villa- Lobos 17 quartets cycle, was nominated for a Grammy award in 2002. Of their two CDs “Brasileiro, works of Mignone”, on the Sono Luminus label, won  a Latin Grammy in 2012.",
      "./home-devstories/musican1.jpg",
    ],
    "Christopher Marlo Jimenez": [
      "Head Developer for Finance and Management Team (A.Y 2023-2024)",
      "Surprisingly, it's neither the programming nor the skills I have picked up as a developer that I will highlight during my stay in the Alliance. No, instead I'm putting into the picture the values of leadership and camaraderie I have come to develop. Here I have met the most interesting people I will ever come across, and it is honestly an honor I get to call them my friends. I have learned from them as they have from me. I have led my peers as they have led me. This two-way communication between me and them will always be my greatest treasure from CMG. My ates and kuyas from the organization have and continue to raise me with the principles and thinking of an Iskolar ng Bayan, and I aim to continue this legacy.",
      "./home-devstories/musican2.jpg",
    ],
    "Danielle Lei Araez": [
      "Developer for Media and Publicity",
      "Joining CMG enabled me to gain new friends and made me feel at ease especially in classes as I get to see fellow members during lecture or laboratory sessions. It also helped me tap on to my collaborative and creative skills as a member of the Media and Publicity team. I am profoundly grateful for CMG for letting me shine and boost my capabilities as an aspiring developer.",
      "./home-devstories/musican3.jpg",
    ],
    "Mark Jay Nicolas": [
      "Alumnus Developer",
      "CMG isn't just an organization; it's a family that fosters growth and support. Being a part of CMG has shown me the true essence of unity and collaboration. Just like a family, its members are always ready to lend a helping hand and provide unwavering support. Together, we've grown, learned, and achieved more than I could have imagined. CMG truly embodies the spirit of a family that's there for each other every step of the way.",
      "./home-devstories/musican1.jpg",
    ],
    "Kenneth Renz Tegrado": [
      "Developer for Academic Affairs",
      "Being a cherished member of this student organization has been an enriching journey that's surpassed all my expectations. It's not just about the skill-building workshops, impactful projects, and leadership opportunities that have given me a new perspective on my potential; it's also about the friendships formed and the sense of belonging that have turned mere colleagues into a close-knit family. This organization has not only enhanced my university experience but also equipped me with invaluable life skills and a network of connections that I'll forever be grateful for, as I confidently stride towards a future shaped by these unforgettable experiences.",
      "./home-devstories/musican2.jpg",
    ],
  };
  // convert the object to an array to iterate through it through the each statement
  let stories = Object.entries(devStories);

  // import SplideJS for the Dev Story Carousel
  import { Splide, SplideSlide, SplideTrack } from "@splidejs/svelte-splide";
  import "@splidejs/svelte-splide/css";

  // Splide Options to autoplay
  const options = {
    rewind: true,
    gap: "1rem",
    autoplay: true,
    arrows: true, // show left and right arrows
    interval: 3000, //
  };
</script>

<section
  id="devstories"
  class="scrollFadeIn py-32 max-sm:mx-4 max-lg:mx-10 max-xl:mx-16 max-3xl:mx-28 3xl:mx-40 z-[1]"
>
  <!-- div class to center the dev story header -->
  <div class="flex flex-col items-center">
    <DevStoriesHeader />
  </div>
  <div class="pt-20 z-1 relative">
    <!-- Gradient Shapes at the Back -->
    <!-- Ellipse Top -->
    <img
      src="/assets/gradient-ellipse.svg"
      alt="Gradient Ellipse"
      width="90"
      height="90"
      class="absolute w-[70px] top-[6%] md:top-[15%] left-[75%] origin-center rotate-45"
    />

    <!-- Ellipse Bottom -->
    <img
      src="/assets/gradient-ellipse.svg"
      alt="Gradient Ellipse"
      width="45"
      height="45"
      class="absolute w-[45px] top-[80%] sm:top-[65%] left-[35%] opacity-40"
    />

    <!-- Hexagon Left -->
    <img
      src="/assets/gradient-hexagon.svg"
      alt="Gradient Hexagon"
      width="140"
      height="162"
      class="absolute w-[140px] top-[30%] md:top-[8%] left-[-8%] md:left-[0%] 2xl:left-[15%]"
    />

    <!-- Hexagon Right -->
    <img
      src="/assets/gradient-hexagon-2.svg"
      alt="Gradient Hexagon"
      width="70"
      height="81"
      class="absolute w-[70px] top-[85%] left-[90%] md:top-[85%] md:left-[70%]"
    />

    <!-- Splide Carousel -->
    <Splide {options} hasTrack={false} aria-label="...">
      <div class="custom-wrapper">
        <SplideTrack>
          {#each stories as [name, [position, story, imageUrl]], index}
            <SplideSlide>
              <DevStoriesTemplate
                {name}
                {position}
                {story}
                {imageUrl}
                {index}
              />
            </SplideSlide>
          {/each}
        </SplideTrack>

        <div class="splide__arrows" />
      </div>
    </Splide>
  </div>
</section>

<style>
  /* so that the image would not be draggable */
  img {
    -drag: none;
    user-select: none;
    -moz-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
    -ms-user-select: none;
  }
</style>
