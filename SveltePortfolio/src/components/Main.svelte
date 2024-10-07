<script>
    import Step from "./Step.svelte";

    let isModalOpen = false;

    let modalImageSrc = "";

    let steps = [
        {
            name: "Simon Says Game using Java",
            icon: "fa-solid fa-list-check",
            description:
                "",
        },
        {
            name: "3D Object Rendering using Python",
            icon: "fa-solid fa-list-check",
            description:
                "Using Python, Pyrr, and OpenGL with GLFW, you can render various geometric shapes like cubes, spheres, and pyramids in real-time 3D environments. The combination of these tools enables efficient rendering and interactive graphics.",
        },

        {
            name: "Gamified History Quiz Site using PHP & MySQL",
            icon: "fa-solid fa-list-check",
            description:
                "A PHP-based history quiz site with MySQL offers dynamic quizzes where users earn points, unlock badges, and climb leaderboards. Gamification enhances learning through fun competition.",
        },
    ];

    let benefits = [
        {
            metric: "10x",
            name: "I Love Frameworks",
            description:
                "I enjoy exploring a wide range of technologies and frameworks to build interactive and engaging applications. My journey includes diving into front-end frameworks like SvelteKit, Tailwind CSS, and Angular, where I've worked on projects ranging from dynamic web apps to gamified learning platforms. I love the creative process of turning ideas into functional, user-friendly experiences..",
        },
        {
            name: "Has a Passion in Game Developing",
            description:
                "I am also passionate about game development and have been learning the Ren'Py engine to create narrative-driven experiences. This journey allows me to blend storytelling with interactive gameplay, tapping into my creativity while mastering the technical aspects of game design..",
        },
        {
            name: "I do code exercises  when I'm bored",
            description:
                "I love creating coding exercises to kill time while enhancing my programming skills. Projects like rendering geometric shapes using Python with Pyrr, GLFW, and OpenGL, as well as developing a mini Java game, allow me to experiment and deepen my understanding of various concepts in software development..",
        },
    ];

        // Function to open the modal with the clicked image
        function openModal(src) {
          modalImageSrc = src;
          isModalOpen = true;
        }

        // Function to close the modal
        function closeModal() {
          isModalOpen = false;
          modalImageSrc = "";
        }
</script>

<!--Intro Page-->

<main class="flex flex-col flex-1 p-4">
    <section
        id="introPage"
        class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
    >
        <div
            class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        >
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-violet-400">Jared Raine</span> Malit
                <br />Front-End
                <span class="poppins text-violet-400">Developer</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My <span class="text-violet-400"> Favorite Languages and Engines</span> includes JavaScript
                (NEXT.JS or SvelteKit), TailwindCSS, Python, Java, C, PHP, C++ and Renpy
            </p>
            <button
                class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950"
                on:click={() => alert('Get in touch button clicked!')}
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </button>
        </div>

        <!--Profile Picture-->

        <div class="relative shadow-2xl grid place-items-center">
            <img
                src={"images/profile.png"}
                alt="Zetane Engine"
                class="object-cover z-[2] max-h-[70vh]"
            />
        </div>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
    </section>

    <!--Creatives Section-->
    
    <section class="py-20 lg:py-32 flex flex-col gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">

            <h6 class="text-large sm:text-xl md:text-2xl">
                A few of my creative endeavors.
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to <span class="poppins text-violet-400">see</span> my work?
            </h3>

            <!--Youtube link-->

        </div>
        <a
            href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
            target="_blank"
            class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-regular fa-circle-play" />
            <p>Watch the video</p>
        </a>

        <!-- Projects -->
         <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
           <!-- Project 1 -->
           <Step step={steps[0]}>
             <p>
               Simon Says Game was developed with the use of
               <strong class="text-violet-400">Thread.sleep();</strong>.

               <!-- Screenshot for Simon Says -->
               <img
                 src="/images/screenshot1.png"
                 alt="Simon Says Game"
                 class="rounded-lg shadow-lg w-full h-auto mt-4 cursor-pointer"
                 on:click={() => openModal('/images/screenshot1.png')}
               />
             </p>
           </Step>
           
       
           <!-- Project 2 -->
           <Step step={steps[1]}>
             <p>
               I developed a 3D rendering code using
               <strong class="text-violet-400">glfw</strong>,
               <strong class="text-violet-400">pyrr</strong>, and
               <strong class="text-violet-400">OpenGL Libraries</strong>.

               <!-- Screenshot for 3D Rendering -->
               <img
                 src="/images/screenshot2.png"
                 alt="3D Rendering"
                 class="rounded-lg shadow-lg w-full h-auto mt-4 cursor-pointer"
                 on:click={() => openModal('/images/screenshot2.png')}
               />
             </p>
           </Step>

       
           <!-- Project 3 -->
           <Step step={steps[2]}>
             <p>
               I made a Gamified Quiz site with the use of
               <strong class="text-violet-400">PHP</strong> and
               <strong class="text-violet-400">MySQL</strong>.

               <!-- Screenshot for Gamified Quiz Site -->
               <img
                 src="/images/screenshot3.png"
                 alt="Gamified Quiz Site"
                 class="rounded-lg shadow-lg w-full h-auto mt-4 cursor-pointer"
                 on:click={() => openModal('/images/screenshot3.png')}
               />
             </p>
           </Step>
         </div>
     
         <!-- Modal -->
         {#if isModalOpen}
           <div class="fixed inset-0 bg-black bg-opacity-75 flex justify-center items-center z-50">
             <div class="relative max-w-3xl mx-auto">
               <button class="absolute top-4 right-4 text-white text-3xl" on:click={closeModal}>
                 &times;
               </button>
               <img src={modalImageSrc} alt="Expanded Image" class="rounded-lg shadow-lg max-w-full h-auto" />
             </div>
           </div>
         {/if}
    </section>

    <!--About me-->

    <section
        id="about"
        class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
    >
        <div
            class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
        >
            <h6 class="text-large sm:text-xl md:text-2xl">
                Want to know more?
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                A bit <span class="poppins text-violet-400">about</span> me.
            </h3>
        </div>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            {#each benefits as benefit, index}
                <div class="flex gap-6 sm:gap-8">
                    <p
                        class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
                    >
                        0{index + 1}
                    </p>
                    <div class="flex flex-col gap-6 sm:gap-8">
                        <h3 class="text-2xl sm:text-3xl md:text-5xl">
                            {benefit.name}
                        </h3>
                        <p>{benefit.description}</p>
                    </div>
                </div>
            {/each}
        </div>
    </section>
</main>