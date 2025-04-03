<script lang="ts">
  import avatar from "$assets/avatar.svg";
</script>

<section id="about" class="py-20 bg-base-200">
  <div class="max-w-4xl mx-auto px-4">
    <h2 class="text-3xl font-bold text-center mb-8">About Me</h2>
    <div class="flex flex-col md:flex-row items-center gap-10">
      <!-- Profile image or avatar -->
      <img
        src={avatar}
        alt="Developer avatar"
        class="w-40 h-40 rounded-full shadow-lg object-cover"
      />

      <!-- About text -->
      <div class="text-center md:text-left">
        <p class="text-lg text-gray-700 dark:text-gray-300 leading-relaxed">
          I’m a Computer Science graduate from the University of Maryland,
          currently pursuing an M.S. in Information Systems Engineering at Johns
          Hopkins. I’ve built games, compilers, and systems using Java, OCaml,
          C, and more, with strong skills in web development, OOP, and data
          structures.
        </p>
        <p
          class="mt-4 text-lg text-gray-700 dark:text-gray-300 leading-relaxed"
        >
          I’ve gained hands-on tech experience at Q Computers and built solid
          customer service skills at JCPenney. Outside of work, I enjoy coding
          side projects, gaming, swimming, and baking.
        </p>
      </div>
    </div>
  </div>
</section>
