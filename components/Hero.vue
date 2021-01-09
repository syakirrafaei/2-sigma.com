<template>
  <section class="relative">
    <div
      class="hero_placeholder bg-orange-900 object-cover shadow-lg relative z-0 transition ease-in-out duration-700"
    ></div>
    <div class="absolute hero_section text-white font-bold">
      <div
        class="flex flex-wrap flex-col px-6 text-center xl:text-left xl:px-20"
      >
        <div class="xl:-ml-10">
          <span class="text-2xl xl:text-3xl"
            >16+ YEARS OF PROVEN IT SOLUTIONS AND TRAININGS</span
          >
        </div>
        <div class="mt-10 mb-4">
          <span class="text-lg xl:text-2xl xl:ml-10">149+</span> satisfied
          clients.
        </div>
        <div class="my-4">
          <span class="text-lg xl:text-2xl xl:ml-40">68+</span> training
          sessions.
        </div>
        <div class="my-4">
          <span class="text-lg xl:text-2xl xl:ml-64">46+</span> projects
          delivered.
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      isLoading: true,
    }
  },
}
</script>
<style scoped>
.hero_section {
  top: 20%;
  left: 0px;
  right: 0px;
}
.hero_placeholder {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(
      to right,
      rgb(255, 255, 255, 0),
      rgba(0, 0, 0, 0.76)
    ),
    linear-gradient(rgba(0, 0, 0, 0.459), rgba(184, 83, 1, 0.445)),
    url('~assets/images/hero.png');
  background-size: cover;
}
@media (min-width: 1280px) {
  .hero_section {
    top: 25%;
    left: 50%;
  }
}
</style>
