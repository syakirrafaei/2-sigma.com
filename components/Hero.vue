<template>
  <div class="relative">
    <video
      v-show="!isLoading"
      ref="myVideo"
      width="100%"
      class="object-cover shadow-lg relative z-0 transition ease-in-out duration-700"
      style="height: 100vh"
      muted
      autoplay
      @ended="onEnd()"
      v-bind:onloadeddata="(isLoading = false)"
    >
      <source src="~assets/videos/hero.mp4" type="video/mp4" />
    </video>
    <img
      v-show="isLoading"
      src="~assets/images/hero.png"
      alt="background hero image"
      class="object-cover shadow-lg relative z-0 transition ease-in-out duration-700"
    />
    <div class="absolute hero_section">
      <div
        class="flex flex-wrap flex-col px-6 text-center xl:text-left xl:px-20"
      >
        <div class="font-bold text-white text-2xl xl:text-3xl">
          16+ YEARS OF PROVEN IT SOLUTIONS AND TRAININGS
        </div>
        <div class="font-bold text-white text-xl mt-10 mb-4">
          <span class="text-lg xl:text-2xl xl:ml-10">149+</span> satisfied
          clients.
        </div>
        <div class="font-bold text-white text-xl my-4">
          <span class="text-lg xl:text-2xl xl:ml-40">68+</span> training
          sessions.
        </div>
        <div class="font-bold text-white text-xl my-4">
          <span class="text-lg xl:text-2xl xl:ml-64">46+</span> projects
          delivered.
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isLoading: true,
    }
  },
  methods: {
    onEnd() {
      this.$refs.myVideo.currentTime = 6
      this.$refs.myVideo.play()
    },
  },
}
</script>
<style scoped>
.hero_section {
  top: 20%;
  left: 0px;
  right: 0px;
}
@media (min-width: 1280px) {
  .hero_section {
    top: 25%;
    left: 50%;
  }
}
</style>
