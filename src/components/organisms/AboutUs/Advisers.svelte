<script>
  const advisers = [
    {
      name: "Sir Fermin Roberto G. Lapitan",
      position: "Senior Adviser",
      testimonial:
        "Happy to have served as the adviser for several years. Keep up the great work with the projects and activities that benefit the ICS students.",
      photo: "/assets/advisers-1.webp",
    },
    {
      name: "Sir John O-Neil Geronimo",
      position: "Junior Adviser",
      testimonial:
        "I've had the privilege of advising CMG, and it's been a remarkable experience. CMG stands out for its proactive efforts in launching programs to aid their fellow students, which have significantly influenced the academic community. Furthermore, some of their members consistently demonstrate impressive coding skills, leading to substantial contributions to the success of various projects. Their effective communication and professionalism have made my role as a junior adviser exceptionally smooth. Their sincere appreciation for the support they receive further strengthens the collaborative and optimistic atmosphere within the organization.",
      photo: "/assets/advisers-2.webp",
    },
  ];
</script>

<div
  id="advisers"
  class="scrollFadeIn advisers flex flex-col justify-center items-center h-fit p-10 md:p-20"
>
  <h3>Advisers</h3>
  <div class="flex flex-col gap-5">
    <!-- {#each advisers as text, index}

    {/each} -->
    <div
      class="advisers__container flex justify-center self-start w-100 gap-10"
    >
      <div class="senior flex flex-row gap-5 text-left items-center xl:w-2/3">
        <img
          src={advisers[0].photo}
          alt="gradient-blur-ellipse"
          class="photo-size md:mr-10"
        />
        <div class="info-container flex flex-col gap-3 justify-self-center">
          <div class="flex flex-col">
            <p class="text-lg font-bold">{advisers[0].name}</p>
            <p class="text-base font-extralight text-slate-500">
              {advisers[0].position}
            </p>
          </div>
          <p class="text-base font-extralight w-100">
            “{advisers[0].testimonial}”
          </p>
        </div>
      </div>
    </div>
    <div class="advisers__container flex justify-center self-start w-100">
      <div class="junior flex flex-row gap-5 text-left items-center xl:w-2/3">
        <div
          class="info-container flex flex-col gap-3 justify-self-center text-right"
        >
          <div class="flex flex-col">
            <p class="text-lg font-bold">{advisers[1].name}</p>
            <p class="text-base font-extralight text-slate-500">
              {advisers[1].position}
            </p>
          </div>
          <p class="text-base font-extralight w-100">
            “{advisers[1].testimonial}”
          </p>
        </div>
        <img
          src={advisers[1].photo}
          alt="gradient-blur-ellipse"
          class="photo-size md:ml-10"
        />
      </div>
    </div>
  </div>
</div>

<style>
  @media (min-width: 0px) and (max-width: 820px) {
    .senior {
      flex-direction: column;
      text-align: center;
      width: 100%;
    }
    .junior {
      flex-direction: column-reverse;
    }
    .junior div {
      text-align: center;
    }
    img {
      margin: 0px;
    }
  }

  .photo-size {
    height: 250px;
    width: 250px;
  }
</style>
