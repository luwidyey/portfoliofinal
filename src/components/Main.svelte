<script>
  import Step from "./Step.svelte";

  let steps = [
    {
      name: "E-commerce",
      description:
        "It is a basketball shoes e-commerce, made in Java GUI. There's a login form, splash screen right after you login and the main page where you'll look at the basketball shoes.",
      href: "https://drive.google.com/file/d/1bygRxl7w195gftN90rJZogiYeXltbcnu/view",
    },
  ];

  let skills = [
    {
      name: "CSS",
    },
    {
      name: "HTML",
    },
    {
      name: "JavaScript",
    },
    {
      name: "TailwindCSS",
    },
    {
      name: "Svelte",
    },
    {
      name: "Java",
    },
  ];

  let benefits = [
    {
      name: "a student",
      description:
        "My name is Louie Jay B. Cania, and I am currently a third year computer science student from Cavite State University - Bacoor Campus. I'm a fan of aethestically pleasing designs, that is one of the reasons why I'm in the front-end development. I’m driven by the endless possibilities in web design and development. My love for visually compelling and intuitive designs motivates me to dive deeper into front-end development, where I get to blend creativity with functionality. I’m always eager to learn new techniques and frameworks that can bring unique, crazy, chaotic, and polished aesthetics to my projects. ",
    },
  ];
</script>

<main class="flex flex-col flex-1 p-4">
  <section
    id="introPage"
    class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
  >
    <div
      class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
    >
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        Hi! I'm <span class="poppins text-red-600">Louie</span> Cania
        <br />Front-end
        <span class="poppins text-red-600">Developer</span>
      </h2>
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img
        src={"images/profile.png"}
        alt="Zetane Engine"
        class="object-cover z-[2] max-h-[70vh]"
      />
    </div>
  </section>
  <section
    class="py-20 lg:py-32 flex flex-col items-center gap-24"
    id="projects"
  >
    <div class="flex flex-col gap-2 text-center">
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        <span class="poppins text-white-0">PROJECTS</span>
      </h3>
    </div>
    <div class="flex justify-center">
      {#each steps as step}
        <Step {step}>
          <p>
            It is a simple basketball shoes e-commerce, made in <strong
              class="text-red-600">Java GUI</strong
            >, There's a login form, splash screen right after you login and the
            main page where you'll look at the basketball shoes.
          </p>
        </Step>
      {/each}
    </div>
  </section>
  <section id="skills" class="py-20 lg:py-32 flex flex-col items-center gap-12">
    <div class="flex flex-col gap-2 text-center">
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        <span class="poppins text-white-0">SKILLS</span>
      </h3>
    </div>
    <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-6 gap-8">
      {#each skills as skill}
        <div class="flex flex-col items-center gap-4">
          <i class={`text-6xl ${skill.icon} ${skill.color}`}></i>
          <h4 class="text-xl font-medium">{skill.name}</h4>
        </div>
      {/each}
    </div>
  </section>
  <section
    id="about"
    class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
  >
    <div
      class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-white after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-white py-4"
    >
      <h6 class="text-large sm:text-xl md:text-2xl">Want to know more?</h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        A bit <span class="poppins text-red-600">about</span> me.
      </h3>
    </div>
    <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
      I am . . .
    </p>
    <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
      {#each benefits as benefit, index}
        <div class="flex gap-6 sm:gap-8">
          <div class="flex flex-col gap-6 sm:gap-8">
            <h3 class="text-2xl sm:text-3xl md:text-5xl">
              {benefit.name}
            </h3>
            <p>{benefit.description}</p>
          </div>
        </div>
      {/each}
    </div>

    <div class="mx-auto -mt-12 italic sm:hidden opacity-50"></div>
  </section>
</main>
