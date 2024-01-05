<script>
  import { Button, HamburgerMenu } from "$components";
  import { page } from "$app/stores";


  let pages = [
    { title: "Home", url: "/" },
    { title: "About Us", url: "/about-us" },
    { title: "Concert", url: "/showcase" },
    { title: "Video", url: "/developers" },
    { title: "Donation", url: "/developers" },
    { title: "Young Musican Console", url: "/developers" },
  ];

  $: currentPath = $page.url.pathname;

  const isActive = (/** @type {string} */ path) => {
    return currentPath === path;
  };

  function handleClick() {
    window.scrollTo({ top: 0, left: 0, behavior: "instant" });
    // string = "You wasted a second of your life :D";
    // buttonVisible = false;
  }

  // let showComponent = true;
  // const handleHover = () => {
  //   showComponent = true;
  // };

  // const handleLeave = () => {
  //   showComponent = false;
  // };
</script>

<header>
  <nav class="p-20 fixed z-50">
    <div class="flex lg:hidden xl:hidden justify-start self-start">
      <HamburgerMenu />
    </div>
  </nav>
  <div class="hoverable-component bg-transparent">
    <!-- {#if showComponent} -->
    <nav class="hovered-section">
      <div
        id="dark-gradient"
        class="flex flex-row justify-between items-center fixed top-0 w-screen pl-10 xl:pl-20 lg:pl-20 pr-20 pb-5 pt-10 lg:pt-3 xl:pt-3 z-50 backdrop-blur-none lg:backdrop-blur-md xl:backdrop-blur-md"
      >
        <div class="hidden lg:grid xl:grid grid-cols-2">
          <a href="/">
            <img
              src="/logo.png"
              alt="The official seal of The Alliance of Musical Student"
              class="140 h-16 w-340"
            />
          </a>
        </div>
        <div class="hidden lg:flex items-center flex justify-end gap-5">
          <ul class="flex flex-row gap-5">
            {#each pages as { title, url }}
              <li>
                <a
                  href={url}
                  class="duration-300 hover:text-base-sky-blue"
                  class:active-link={currentPath === url}
                  on:click={() => {
                    window.scrollTo({ top: 0, left: 0, behavior: "instant" });
                  }}>{title}</a
                >
              </li>
            {/each}
          </ul>
          <a href="/contact-us">
            <Button onClick={handleClick}>Contact Us</Button>
          </a>
        </div>
      </div>
    </nav>
    <!-- {/if} -->
  </div>
</header>

<style>
  .active-link {
    margin-top: 1px;
    border: 18px solid;
    border-image-slice: 1;
    border-width: 3px;
    border-left: 0;
    border-right: 0;
    border-top: 0;
    border-image-source: linear-gradient(
      270deg,
      rgba(46, 55, 146, 0) 0%,
      #2e3792 27.6%,
      #00f5f1 74.48%,
      rgba(0, 245, 241, 0) 100%
    );
    color: #00f5f1;
  }

  .active-link:hover {
    color: #f4f1ff;
  }
  #dark-gradient {
    background: linear-gradient(
      180deg,
      rgba(223, 237, 244, 0.8) 0%,
      rgba(181, 221, 237, 0.6) 30%,
      rgba(123, 162, 200, 0.45) 80%
    );
  }
</style>
