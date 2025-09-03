<script lang="ts">
  import { onMount } from "svelte";
  const baseUrl = import.meta.env.VITE_BASE_URL || "http://localhost:5173";
  let isOpen = false;
  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.pageYOffset > 50;
    };

    // Add scroll event listener
    window.addEventListener("scroll", handleScroll);

    const hamburger = document.getElementById("hamburger");
    const navMenu = document.getElementById("nav-menu");

    if (hamburger && navMenu) {
      hamburger.addEventListener("click", () => {
        isOpen = !isOpen;
        hamburger.classList.toggle("hamburger-active");
        navMenu.classList.toggle("hidden", !isOpen);
        // document.body.classList.toggle("overflow-hidden", isOpen);
      });
    }

    // Cleanup function
    return () => {
      window.removeEventListener("scroll", handleScroll);
    };
  });
</script>

<header
  class={{
    "absolute top-0 left-0 w-full flex items-center z-10 transition-all duration-300":
      isOpen || isScrolled,
    "fixed top-0 bg-white opacity-70 backdrop-blur-[5px] shadow-xl z-10 inset-shadow-nav":
      isScrolled,
    "bg-transparent": !isScrolled,
  }}
>
  <div class="container">
    <div class="flex items-center justify-between relative">
      <div class="px-4">
        <a
          href={baseUrl}
          class="font-bold text-primary text-lg block py-6"
          >Neno Arisma Space's</a
        >
      </div>
      <div class="flex items-center px-4">
        <!-- svelte-ignore a11y_consider_explicit_label -->
        <button
          id="hamburger"
          type="button"
          class="block absolute right-4 lg:hidden"
        >
        <span
    class="hamburger-line origin-top-left transition duration-300 ease-in-out"
    class:rotate-45={isOpen}
  ></span>
  <span
    class="hamburger-line transition duration-300 ease-in-out"
    class:scale-0={isOpen}
  ></span>
  <span
    class="hamburger-line origin-bottom-left transition duration-300 ease-in-out"
    class:-rotate-45={isOpen}
  ></span>
        </button>
        <nav
          class="hidden absolute py-5 bg-white shadow-lg rounded-lg max-w-[250px] w-full right-4 top-full lg:block lg:static lg:bg-transparent lg:max-w-full lg:shadow-none lg:rounded-none"
          id="nav-menu"
        >
          <ul class="block lg:flex">
            <li class="group">
              <a
                href="#about"
                class="text-base text-dark flex py-2 mx-8 group-hover:text-primary"
                >About</a
              >
            </li>
            <li class="group">
              <a
                href="#services"
                class="text-base text-dark flex py-2 mx-8 group-hover:text-primary"
                >Skillset</a
              >
            </li>
            <li class="group">
              <a
                href="#portfolio"
                class="text-base text-dark flex py-2 mx-8 group-hover:text-primary"
                >Portfolio</a
              >
            </li>
            <li class="group">
              <a
                href="#contact"
                class="text-base text-dark flex py-2 mx-8 group-hover:text-primary"
                >Contact</a
              >
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </div>
</header>
