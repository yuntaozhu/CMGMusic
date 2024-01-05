<!-- Hero Section -->
<script>
    import { Statistics } from "$components";
</script>

<section class="tag container mx-auto relative">
    <div
        class="flex flex-col min-h-[90vh] mx-4 pt-10 gap-5 md:flex-row md:align-center md:justify-evenly md:gap-10 2xl:gap-2 max-[480px]:min-h-[100vh] max-[480px]:mb-20"
    >
        <!-- CMG Logo -->
        <div
            class="pt-4 ss:pt-12 md:pt-0 flex justify-center items-center md:flex-1 3xl:max-w-screen-sm floating"
        >
            <img
                src="/assets/hero-banner.webp"
                alt="The seal of CMG placed on top of a glass object."
                width="500"
                height="500"
                class="max-w-xs 2xl:max-w-sm 3xl:max-w-lg m-auto"
            />
        </div>
        <!-- Hero Caption -->
        <div
            class="flex flex-col md:justify-center md:flex-1 gap-6 md:max-w-xl 3xl:max-w-2xl"
        >
            <div class="flex flex-col gap-1">
                <h1
                    class="text-4xl font-bold leading-tight lg:text-5xl md:leading-snug tracking-wide"
                >
                    CMG Young Musican Console
                </h1>
                <p
                    class="font-thin text-slate-200 md:max-w-sm text-sm 3xl:text-base 3xl:max-w-xl"
                >
                    Originally, chamber music referred to a type of classical music that was performed in a small space such as a house or a palace room.
                    There were far fewer instruments then found in an orchestra and no conductor to guide the musicians.
                    Today, the tradition of chamber music remains very similar to its origins in terms of the size of the venue and the number of instruments used.
                    Typically, a chamber orchestra is composed of 40 or fewer musicians.
                    Because of the limited number of instruments, each instrument plays an equally important role.
                </p>
            </div>
            <div class="flex flex-col gap-4">
                <p class="text-slate-200 font-light max-w-fit">
                    Alliance of Computer Science Students — <br />University of
                    the Philippines Los Baños
                </p>
                <Statistics />
            </div>
        </div>
    </div>
    <!-- Scroll Down Mouse Graphic Animation -->
    <div
        class="max-[480px]:hidden w-8 h-10 border-2 rounded-full m-auto pt-2 mt-6 sm:mt-0 mb-10"
    >
        <div class="w-1 h-3 bg-white rounded-md animate-bounce m-auto" />
    </div>
</section>
