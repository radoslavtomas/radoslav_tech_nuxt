<template>
  <div class="container mx-auto px-4 text-center mt-4 md:mt-8 lg:mt-16 pb-4 md:pb-8 lg:pb-16">
    <h1 class="text-2xl mb-1 text-gray-700">Radoslav Tomas</h1>
    <h3 class="text-xs font-light mb-6 md:mb-12">Full-stack Web Development</h3>
    <div class="container mx-auto px-4 flex justify-center">
      <img class="w-7/12 md:w-5/12 lg:w-4/12" src="~/assets/img/laravue.svg" alt="developer" />
    </div>

    <div class="mt-6 md:mt-12 font-light">
      <p>Custom solutions in a simple and clean way.</p>
      <p>I specialise in the Laravel framework on the backend, Vue.js on the frontend.</p>
    </div>

    <div class="mt-4 font-light">
      <p>Currently developing great code and manners in Liverpool, UK.</p>
      <nuxt-link
        class="inline-block rounded text-blue-600 border border-blue-600 bg-gray-200 hover:bg-gray-300 px-4 py-2 font-normal mt-10"
        to="/contact"
      >Contact me</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  components: {
    //
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
