<script>
  export let y;

  export let tabs = [
    { name: "PROJECTS", link: "#projects" },
    { name: "SKILLS", link: "#skills" },
    { name: "ABOUT ME", link: "#about" },
  ];

  let isMenuOpen = false;

  function scrollToSection(link) {
    const sectionId = link.replace("#", "");
    const section = document.getElementById(sectionId);
    if (section) {
      section.scrollIntoView({ behavior: "smooth" });
    }
    // Close menu after clicking a link (mobile view)
    isMenuOpen = false;
  }

  function closeMenu() {
    isMenuOpen = false;
  }
</script>

<header
  class={"sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-b border-solid " +
    (y > 0
      ? " py-4 bg-red-950 border-white"
      : " py-6 bg-transparent border-transparent")}
>
  <h1 class="font-medium">
    <b class="font-bold poppins">LJ</b>
  </h1>
  <div class="sm:flex items-center gap-4 hidden">
    {#each tabs as tab}
      <a
        href={tab.link}
        class="duration-200 hover:text-red-600"
        on:click={() => scrollToSection(tab.link)}
      >
        <p>{tab.name}</p>
      </a>
    {/each}
    <button
      on:click={() =>
        document.getElementById("foot").scrollIntoView({ behavior: "smooth" })}
      class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950"
    >
      <div
        class="absolute top-0 right-full w-full h-full bg-red-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
      ></div>
      <h4 class="relative z-9">Contact Me &rarr;</h4>
    </button>
  </div>
  <div class="sm:hidden flex items-center">
    <button
      class="text-white"
      on:click={() => (isMenuOpen = !isMenuOpen)}
      aria-label="Toggle menu"
    >
      <svg
        class="w-8 h-8"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16m-7 6h7"
        />
      </svg>
    </button>
    {#if isMenuOpen}
      <div
        class="absolute top-16 right-6 bg-red-950 text-white rounded-lg shadow-lg p-4 flex flex-col gap-4"
      >
        {#each tabs as tab}
          <a
            href={tab.link}
            class="duration-200 hover:text-red-600"
            on:click={() => scrollToSection(tab.link)}
          >
            <p>{tab.name}</p>
          </a>
        {/each}
        <button
          on:click={() => {
            document
              .getElementById("foot")
              .scrollIntoView({ behavior: "smooth" });
            closeMenu();
          }}
          class="px-5 py-2 rounded-full bg-white text-slate-950"
        >
          Contact Me &rarr;
        </button>
      </div>
    {/if}
  </div>
</header>
