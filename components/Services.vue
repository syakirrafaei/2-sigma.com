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
            <div class="grid md:grid-cols-6 gap-4 gap-y-16">
              <div class="col-start-1 col-span-2">
                <div class="w-16 md:w-32">
                  <div
                    class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
                  >
                    <img
                      src="~/assets/images/training.svg"
                      alt="IT software training"
                      class="h-16 w-16 md:h-32 md:w-32 my-auto p-2 pb-4"
                    />
                    <div
                      class="text-xs xl:text-base text-center font-semibold mt-2"
                    >
                      Training
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-start-3 col-span-2">
                <div class="w-16 md:w-32">
                  <div
                    class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-xl bg-gray-900 border border-orange-700"
                  >
                    <img
                      src="~/assets/images/web-development.svg"
                      alt="web development"
                      class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pb-4"
                    />
                    <div
                      class="text-xs xl:text-base text-center font-semibold mt-2"
                    >
                      Website
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-start-5 col-span-2">
                <div class="w-16 md:w-32">
                  <div
                    class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
                  >
                    <img
                      src="~/assets/images/mobile-development.svg"
                      alt="mobile development"
                      class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pt-2 pb-4"
                    />
                    <div
                      class="text-xs xl:text-base text-center font-semibold mt-2"
                    >
                      Mobile App
                    </div>
                  </div>
                </div>
              </div>

              <div class="col-start-2 col-end-4">
                <div class="w-16 md:w-32">
                  <div
                    class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
                  >
                    <img
                      src="~/assets/images/it_infrastructure.svg"
                      alt="IT infrastructure"
                      class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pt-2 pb-4"
                    />
                    <div
                      class="text-xs xl:text-base text-center font-semibold mt-2"
                    >
                      IT Infrastructure
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-end-6 col-span-2">
                <div class="w-16 md:w-32">
                  <div
                    class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
                  >
                    <img
                      src="~/assets/images/consultancy.svg"
                      alt="consultancy"
                      class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pt-2 pb-4"
                    />
                    <div
                      class="text-xs xl:text-base text-center font-semibold mt-2"
                    >
                      Consultancy
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="w-full xl:w-2/5 pt-10 mx-auto">
        <lottie :options="lottieOptions" @animCreated="handleAnimation" />
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
<style>
.bg-section {
  background: transparent
    linear-gradient(1deg, #17141b 0%, #18151c 10%, #17141b 92%, #160100 100%) 0%
    0% no-repeat padding-box;
}
</style>
