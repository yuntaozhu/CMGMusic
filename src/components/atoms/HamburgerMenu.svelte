<script>
  import { Button } from "$components";
  let menuState = false;

  function toggleMenu() {
    menuState = !menuState;
  }

  let pages = [
    { title: "Home", url: "/" },
    { title: "About Us", url: "/about-us" },
    { title: "Showcase", url: "/showcase" },
    { title: "Video", url: "/developers" },
    {title: "CMG Week", url: ""},
  ];

  function handleClick() {
    // string = "You wasted a second of your life :D";
    // buttonVisible = false;
  }

  function closeHamburger() {
    menuState = false;
  }
</script>

<!-- <div class="menu"> -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div class="menu-container p-5 rounded-md">
  <div class="flex flex-row justify-between gap-5 items-center">
    <div class="w-50 h-50">
      <img
        src="/logo.png"
        alt="The official seal of The Alliance of Musical"
        class="h-12 w-12"
      />
    </div>
    {#if !menuState}
      <div class=" w-[0.1rem] h-8 bg-neutral-50" />
    {/if}
    <div class="w-50 h-50">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
      <label for="menu-toggle" class="cursor-pointer" on:click={toggleMenu}>
        <div class="w-7 h-[0.125rem] bg-neutral-50" />
        <div class="w-7 h-[0.125rem] mt-2 bg-neutral-50" />
        <div class="w-7 h-[0.125rem] mt-2 bg-neutral-50" />
      </label>
    </div>
  </div>
  <div class="flex flex-row gap-3 justify-star self-start">
    {#if menuState}
      <ul>
        {#each pages as { title, url }}
          <li class="border-b p-2">
            <a on:click={closeHamburger} href={url}>{title}</a>
          </li>
        {/each}
        <div class="mt-3">
          <a on:click={closeHamburger} href="/contact-us"
            ><Button onClick={handleClick}>Contact Us</Button></a
          >
        </div>
      </ul>
    {/if}
  </div>
</div>

<!-- </div> -->

<style>
  .menu-container {
    background-color: var(--color-dark-blue);
    box-shadow: 0 0 5px rgba(255, 255, 255, 0.1);
  }

  li:last-child,
  li:nth-child(4) {
    border-bottom: none;
  }
</style>
