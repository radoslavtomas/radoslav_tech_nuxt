<template>
  <div>
    <div class="min-h-screen bg-gray-300 font-body">
      <header
        class="w-full px-4 py-4 bg-gray-700 text-white shadow flex justify-between items-center flex-col md:flex-row"
      >
        <h1 class="text-xl">Radoslav Tomas</h1>
        <div>
          <nuxt-link to="/">Home</nuxt-link>
          <nuxt-link to="/projects" class="ml-2">Projects</nuxt-link>
          <nuxt-link to="/contact" class="ml-2">Contact</nuxt-link>
        </div>
      </header>
      <nuxt />
    </div>

    <footer
      class="w-full px-4 py-4 bg-gray-700 text-white shadow flex justify-between items-center"
    >
      <h1>Radoslav Tomas</h1>
      <div>
        <p class="font-light">٩(◕‿◕｡)۶</p>
      </div>
    </footer>
  </div>
</template>

<style>
.nuxt-link-exact-active {
  @apply text-teal-300;
}
</style>
