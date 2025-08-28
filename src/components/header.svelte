<script lang="ts">
  const baseUrl = import.meta.env.VITE_BASE_URL || "http://localhost:5173";
  import { onMount } from "svelte";
  let isOpen = false;

  console.log("Base URL:", baseUrl);

  onMount(() => {
    const hamburger = document.getElementById("hamburger");
    window.onscroll = () => {
      const header = document.querySelector("header") as HTMLElement | null;
      if (header) {
        const fixedNav = header.offsetTop;
        if (window.pageYOffset > fixedNav) {
          header.classList.add("navbar-fixed");
        } else {
          header.classList.remove("navbar-fixed");
        }
      }
    };

    if (hamburger) {
      hamburger.addEventListener("click", () => {
        isOpen = !isOpen;
        hamburger.classList.toggle("hamburger-active");
        document.body.classList.toggle("overflow-hidden", isOpen);
      });
    }
  });
</script>

<header
  class="bg-transparent absolute top-0 left-0 w-full flex items-center z-10"
>
  <div class="container">
    <div class="flex items-center justify-between relative">
      <div class="px-4">
        <a href={baseUrl} class="font-bold text-primary text-lg block py-6"
          >Neno Arisma</a
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
          ></span>
          <span class="hamburger-line transition duration-300 ease-in-out"
          ></span>
          <span
            class="hamburger-line origin-bottom-left transition duration-300 ease-in-out"
          ></span>
        </button>
      </div>
    </div>
  </div>
</header>
