<template>
  <div>
    <div class="bg-about px-16">
      <div class="flex flex-row flex-wrap text-white py-40">
        <div class="w-full xl:w-1/2">
          <div
            class="w-full text-4xl text-center xl:text-left font-semibold text-white mb-2"
          >
            Our Clients
          </div>
          <div class="mt-6 xl:mt-2 w-full text-lg">
            {{ metas.content }}
          </div>
        </div>
        <div class="w-full xl:w-1/2">
          <img src="" alt="" class="mx-auto h-40" />
        </div>
      </div>
    </div>
    <section class="px-16 py-32 bg-section">
      <VueSlickCarousel v-if="clients.length > 0" v-bind="settings">
        <img
          v-for="client in clients"
          :key="client.id"
          :src="`https://api.2-sigma.com${client.client_logo.url}`"
          :alt="client.client_name"
        />
      </VueSlickCarousel>
    </section>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const clients = await $axios.$get('/client-logos')
    const metas = await $axios.$get('/our-clients')
    return { clients, metas }
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
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 6,
              slidesToScroll: 6,
              infinite: true,
              dots: true,
            },
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3,
              initialSlide: 2,
            },
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
              rows: 1,
            },
          },
        ],
      },
    }
  },
  head() {
    return {
      title: this.metas.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.metas.meta_description,
        },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.metas.meta_title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.metas.meta_description,
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content:
            'https://firebasestorage.googleapis.com/v0/b/gwcqp-40547.appspot.com/o/sigmabanner-01.jpg?alt=media&token=d8905924-34e1-49c9-be25-8c4b41073637',
        },
        {
          hid: 'twitter:image:alt',
          name: 'twitter:image:alt',
          content: this.metas.meta_title,
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.metas.meta_title,
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.metas.meta_description,
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content:
            'https://firebasestorage.googleapis.com/v0/b/gwcqp-40547.appspot.com/o/sigmabanner-01.jpg?alt=media&token=d8905924-34e1-49c9-be25-8c4b41073637',
        },
        {
          hid: 'og:image:secure_url',
          property: 'og:image:secure_url',
          content:
            'https://firebasestorage.googleapis.com/v0/b/gwcqp-40547.appspot.com/o/sigmabanner-01.jpg?alt=media&token=d8905924-34e1-49c9-be25-8c4b41073637',
        },
        {
          hid: 'og:image:alt',
          property: 'og:image:alt',
          content: this.metas.meta_description,
        },
      ],
    }
  },
}
</script>
