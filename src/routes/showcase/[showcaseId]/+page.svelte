<!--
    kahit ano
 -->

<script>
    // @ts-nocheck

    import {
        ShowcaseHeader,
        NavBar,
        ShowcaseImage,
        ShowcaseDescription,
        ShowcaseGallery,
        ShowcaseDevs,
    } from "$components";
    import { data } from "$components/organisms/Showcase/data.js";
    import { page } from "$app/stores";
    const showcaseId = $page.params.showcaseId;

    let contents = "";
    let contentTitle = "";
    let words = showcaseId.split("-");

    if (words.length > 0) {
        contents = words[0];

        words.splice(0, 1);
        contentTitle = words.join(" ");
    }
</script>

  <head>
        {#each data[contents] as content}
            {#if content.title.toLowerCase() === contentTitle}
                <title>{content.title} - Concert</title>
            {/if}

        {/each}
  </head>

  <div class="min-h-screen flex flex-col md:items-center showcase-background pt-10 md:pt-20 pb-10 md:pb-20 gap-10 lg:gap-20 relative z-20">
    <ShowcaseHeader contents = {contents} contentTitle = {contentTitle}/>
    <ShowcaseImage contents = {contents} contentTitle = {contentTitle}/>
    <ShowcaseDescription contents = {contents} contentTitle = {contentTitle}/>
    <ShowcaseGallery contents = {contents} contentTitle = {contentTitle}/>
    {#if contents === "projects"}
        <ShowcaseDevs {contentTitle} />
    {/if}
</div>

<style>
    .showcase-background {
        background-image: url("/homebackground.png");
        background-repeat: no-repeat;
        background-size: cover;
    }
</style>
