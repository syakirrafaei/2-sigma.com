<template>
  <div>
    <div
      class="absolute hidden xl:flex xl:flex-wrap xl:flex-row w-full bg-transparent px-12 py-6 text-white font-semibold z-10"
    >
      <div class="flex w-2/5 text-center">
        <nuxt-link
          to="/about"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
          >About Us</nuxt-link
        >
        <nuxt-link
          to="/our-services"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
          >Our Services</nuxt-link
        >
        <div class="w-full">Our Clients</div>
      </div>
      <nuxt-link
        to="/"
        class="w-1/5 text-center font-bold hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
        >TWO SIGMA</nuxt-link
      >
      <div class="flex w-2/5 text-center">
        <div class="w-full">Training Offered</div>
        <div class="w-full">Contact Us</div>
        <div class="w-full">Careers</div>
      </div>
    </div>
    <div class="xl:hidden fixed top-0 right-0 mt-6 mr-6" style="z-index: 99">
      <svg
        class="w-10 h-10 text-white"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
        @click="showMenu = !showMenu"
      >
        <path
          v-if="showMenu === false"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        ></path>
        <path
          v-else
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        ></path>
      </svg>
    </div>
    <transition name="fade">
      <div
        v-show="showMenu"
        class="fixed top-0 bottom-0 left-0 right-0 bg-black z-50"
        style="--bg-opacity: 0.9"
      >
        <div
          class="flex flex-col flex-wrap text-white text-center text-2xl font-semibold px-6 py-12 mt-20"
        >
          <nuxt-link to="/about" class="mb-8">About Us</nuxt-link>
          <div class="mb-8">Our Services</div>
          <div class="mb-8">Our Clients</div>
          <div class="mb-8">Training Offered</div>
          <div class="mb-8">Contact Us</div>
          <div class="mb-8">Careers</div>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showMenu: false,
    }
  },
  watch: {
    showMenu: {
      immediate: true,
      handler(showMenu) {
        if (process.client) {
          if (showMenu) document.body.style.setProperty('overflow', 'hidden')
          else document.body.style.removeProperty('overflow')
        }
      },
    },
  },
}
</script>
