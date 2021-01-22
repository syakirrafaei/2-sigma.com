<template>
  <section class="h-screen w-full bg-section p-16">
    <div class="inline-block">
      <div class="text-3xl font-bold text-orange">Our Happy Clients.</div>
      <div class="block py-1 divider-orange opacity-75"></div>
    </div>
    <div class="flex flex-row flex-wrap text-white my-8">
      <div class="w-full xl:w-3/5">
        <p class="xl:pr-64 text-lg">
          After over several years in business, Two Sigma Technologies has
          served literally hundreds of satisfied clients.
        </p>
        <div class="flex flex-row flex-wrap mt-16"></div>
      </div>
    </div>

    <VueSlickCarousel v-if="clients.length > 0" v-bind="settings">
      <img
        v-for="client in clients"
        :key="client.id"
        :src="`https://api.2-sigma.com${client.client_logo.url}`"
        :alt="client.client_name"
      />
    </VueSlickCarousel>
  </section>
</template>
<script>
export default {
  props: {
    clients: Array,
  },
  data() {
    return {
      settings: {
        dots: true,
        dotsClass: 'slick-dots custom-dot-class',
        edgeFriction: 0.35,
        infinite: false,
        speed: 500,
        slidesToShow: 6,
        slidesToScroll: 1,
      },
    }
  },
}
</script>
<style scoped>
.bg-section {
  background: transparent linear-gradient(0deg, #9b4930 0%, #17141b 100%) 0% 0%
    no-repeat padding-box;
}
</style>
