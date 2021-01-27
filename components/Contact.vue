<template>
  <section class="h-screen w-full bg-section p-16 -mt-1">
    <div class="inline-block">
      <div class="text-3xl font-bold text-white">Contact Us.</div>
      <div class="block py-1 bg-white opacity-75"></div>
    </div>
    <div class="flex flex-row flex-wrap text-white my-8">
      <div class="w-full xl:w-1/2">
        <h3 class="text-xl text-gray-900 font-semibold">
          You can locate us at:
        </h3>
        <p class="mb-8 xl:w-1/2">
          {{ hero.Address }}
        </p>
        <h3 class="text-xl text-gray-900 font-semibold">
          Contact Information:
        </h3>
        <ul class="text-lg">
          <li>{{ hero.Contact1 }}</li>
          <li></li>
          <li>{{ hero.Contact2 }}</li>
        </ul>
      </div>
      <div class="mt-8 xl:mt-0 w-full xl:w-1/2">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15933.596955824112!2d101.6926258!3d3.2505418!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xa957d5a0dbe53cc8!2sTwo%20Sigma%20Technologies!5e0!3m2!1sen!2smy!4v1611347951161!5m2!1sen!2smy"
          frameborder="0"
          style="border: 0"
          allowfullscreen=""
          aria-hidden="false"
          tabindex="0"
          class="rounded-xl h-64 mx-auto shadow-lg w-full"
        ></iframe>
      </div>
    </div>
  </section>
</template>
<style scoped>
.bg-section {
  background: transparent
    linear-gradient(0deg, #9c513a 0%, #b16634 51%, #9b4930 100%) 0% 0% no-repeat
    padding-box;
}
</style>
<script>
export default {
  props: {
    hero: Object,
  },
  data() {
    return {
      isLoading: true,
    }
  },
}
</script>
