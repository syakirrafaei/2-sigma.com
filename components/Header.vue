<template>
  <div>
    <div
      class="absolute hidden xl:flex xl:flex-wrap xl:flex-row w-full bg-transparent px-12 py-6 text-white font-semibold z-10"
    >
      <div class="flex w-2/5 text-center">
        <nuxt-link
          to="/about"
          :class="$nuxt.$route.path === '/about' ? activeClass : ''"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
          @click="setActive('about')"
          >About Us</nuxt-link
        >
        <nuxt-link
          to="/our-services"
          :class="$nuxt.$route.path === '/our-services' ? activeClass : ''"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
          >Our Services</nuxt-link
        >
      </div>
      <nuxt-link
        to="/"
        :class="$nuxt.$route.path === '/' ? activeClass : ''"
        class="w-1/5 text-center font-bold hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
        >TWO SIGMA</nuxt-link
      >
      <div class="flex w-2/5 text-center">
        <nuxt-link
          to="/our-clients"
          :class="$nuxt.$route.path === '/our-clients' ? activeClass : ''"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
          >Our Clients</nuxt-link
        >
        <nuxt-link
          :to="{ path: '/', hash: '#contact' }"
          :class="$nuxt.$route.path === '/#contact' ? activeClass : ''"
          class="w-full hover:text-orange-600 border-b-2 border-transparent hover:border-orange-700 pb-2"
        >
          Contact Us
        </nuxt-link>
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
          <nuxt-link to="/" class="mb-8" @click.native="showMenu = !showMenu"
            >Home</nuxt-link
          >
          <nuxt-link
            to="/about"
            class="mb-8"
            @click.native="showMenu = !showMenu"
            >About Us</nuxt-link
          >
          <nuxt-link
            to="/our-services"
            class="mb-8"
            @click.native="showMenu = !showMenu"
            >Our Services</nuxt-link
          >
          <nuxt-link
            to="/our-clients"
            class="mb-8"
            @click.native="showMenu = !showMenu"
            >Our Clients</nuxt-link
          >
          <nuxt-link
            to="{ path: '/', hash: '#contact' }"
            class="mb-8"
            @click.native="showMenu = !showMenu"
            >Contact Us</nuxt-link
          >
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
      activeClass:
        'border-orange-700 text-orange-600 border-b-2 border-transparent',
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
