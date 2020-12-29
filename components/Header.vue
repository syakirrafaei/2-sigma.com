<template>
  <div>
    <div
      class="fixed hidden xl:flex xl:flex-wrap xl:flex-row w-full bg-transparent px-12 py-6 text-white font-semibold z-10"
    >
      <div class="flex w-2/5 text-center">
        <div class="w-full">About Us</div>
        <div class="w-full">Our Services</div>
        <div class="w-full">Our Clients</div>
      </div>
      <div class="w-1/5 text-center">TWO SIGMA</div>
      <div class="flex w-2/5 text-center">
        <div class="w-full">Training Offered</div>
        <div class="w-full">Contact Us</div>
        <div class="w-full">Careers</div>
      </div>
    </div>
    <div class="absolute top-0 right-0 mt-6 mr-6" style="z-index: 99">
      <svg
        @click="showMenu = !showMenu"
        class="w-10 h-10 text-white"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
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
        class="absolute top-0 bottom-0 left-0 right-0 bg-black z-50"
        style="--bg-opacity: 0.9"
      >
        <div
          class="flex flex-col flex-wrap text-white text-center text-2xl font-semibold px-6 py-12 mt-20"
        >
          <div class="mb-4">About Us</div>
          <div class="mb-4">Our Services</div>
          <div class="mb-4">Our Clients</div>
          <div class="mb-4">Training Offered</div>
          <div class="mb-4">Contact Us</div>
          <div class="mb-4">Careers</div>
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
}
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
