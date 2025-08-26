<script lang="ts">
  import { Instagram, Github, Mail, Linkedin } from "@lucide/svelte";
</script>

<div class="container">
  <div class="flex flex-wrap">
    <div class="w-full px-4 mb-10 lg:w-1/2">
      <h4 class="font-bold uppercase text-primary text-lg mb-3">About Me</h4>
      <h2 class="font-bold text-slate-900 text-3xl mb-5 max-w-md lg:text-4xl ">
        I am a passionate developer with a love for creating innovative
        solutions.
      </h2>
      <p class="font-medium text-base text-slate-500 max-w-xl lg:text-lg">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quae
        cupiditate ratione sed odio ab mollitia commodi voluptate unde eum et.
      </p>
    </div>
    <div class="w-full px-4 lg:w-1/2 lg:pt-10">
      <h3 class="font-semibold text-slate-900 text-2xl mb-4 lg:text-3xl">Let's Connect</h3>
      <p class="font-medium text-base text-slate-500 mb-6 lg:text-lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut,
        consectetur.
      </p>
      <div class="flex items-center">
        <!-- Instagram -->
        <a
          aria-label="Instagram"
          href="https://instagram.com/nenoarisma"
          target="_blank"
          class="w-9 h-9 mr-3 rounded-full flex items-center justify-center border border-slate-300 hover:border-primary hover:bg-primary hover:text-white"
        >
          <Instagram />
        </a>
        <!-- Github -->
        <a
          aria-label="Github"
          href="https://github.com/nenofetch"
          target="_blank"
          class="w-9 h-9 mr-3 rounded-full flex items-center justify-center border border-slate-300 hover:border-primary hover:bg-primary hover:text-white"
        >
          <Github />
        </a>
        <!-- Email -->
        <a
          aria-label="Email"
          href="mailto:nenoarisma@gmail.com"
          target="_blank"
          class="w-9 h-9 mr-3 rounded-full flex items-center justify-center border border-slate-300 hover:border-primary hover:bg-primary hover:text-white"
        >
          <Mail />
        </a>
        <!-- LinkedIn -->
        <a
          aria-label="LinkedIn"
          href="https://linkedin.com/in/nenoarisma"
          target="_blank"
          class="w-9 h-9 mr-3 rounded-full flex items-center justify-center border border-slate-300 hover:border-primary hover:bg-primary hover:text-white"
        >
          <Linkedin />
        </a>
      </div>
    </div>
  </div>
</div>
