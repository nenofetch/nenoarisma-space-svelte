<script lang="ts">
  import About from "./components/about.svelte";
  import Header from "./components/header.svelte";
  import Hero from "./components/hero.svelte";
</script>

<main class="min-h-screen">
  <!--> Header Section Start -->
  <Header />
  <!--> Header Section End</!-->
  <!-- Hero Section Start -->
  <section id="hero" class="pt-36">
    <Hero />
  </section>
  <!-- Hero Section End -->
  <!-- About Section Start -->
  <section id="about" class="pt-36 pb-32">
    <About />
  </section>
  <!-- About Section End -->
</main>
