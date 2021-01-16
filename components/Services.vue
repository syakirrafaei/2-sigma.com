<template>
  <section class="min-h-screen w-full bg-section p-16">
    <div class="inline-block">
      <div class="text-3xl font-bold text-orange">
        Supercharge your business.
      </div>
      <div class="block py-1 divider-orange opacity-75"></div>
    </div>
    <div class="flex flex-row flex-wrap text-white my-8">
      <div class="w-full xl:w-3/5">
        <p class="xl:pr-64 text-lg">
          Driven by today’s competitive environment and business needs, we have
          grown tremendously by expanding our operation into several distinct
          businesses involves:
        </p>
        <div class="flex flex-row flex-wrap mt-16 mb-10">
          <div class="w-full">
            <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
              <div class="w-20">
                <img
                  src="~/assets/images/training.svg"
                  alt="training with two sigma technologies"
                  class="h-20 w-20"
                />
                <div class="text-center font-semibold mt-2">Training</div>
              </div>
              <div class="w-24">
                <img
                  src="~/assets/images/web-development.svg"
                  alt="web development with two sigma technologies"
                  class="h-20 w-20"
                />
                <div class="text-center font-semibold mt-2">
                  Web Development
                </div>
              </div>
              <div class="w-24">
                <img
                  src="~/assets/images/mobile-development.svg"
                  alt="mobile development with two sigma technologies"
                  class="h-20 w-20"
                />
                <div class="text-center font-semibold mt-2">
                  Mobile Development
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="w-full xl:w-2/5 mx-auto">
        <lottie
          width="100%"
          :options="lottieOptions"
          @animCreated="handleAnimation"
        />
      </div>
    </div>
  </section>
</template>
<script>
import lottie from 'vue-lottie/src/lottie.vue'
import * as animationData from '~/assets/lf30_editor_8jyim1di.json'
export default {
  components: {
    lottie,
  },
  data() {
    return {
      anim: null, // for saving the reference to the animation
      lottieOptions: { animationData: animationData.default },
    }
  },
  methods: {
    handleAnimation(anim) {
      this.anim = anim
    },
  },
}
</script>
<style scoped>
.bg-section {
  background: transparent
    linear-gradient(1deg, #17141b 0%, #18151c 10%, #17141b 92%, #160100 100%) 0%
    0% no-repeat padding-box;
}
</style>
