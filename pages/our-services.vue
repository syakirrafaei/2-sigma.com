<template>
  <div>
    <section class="bg-about px-16">
      <div class="flex flex-row flex-wrap text-white py-40">
        <div class="w-full xl:w-1/2">
          <div
            class="w-full text-4xl text-center xl:text-left font-semibold text-white mb-2"
          >
            Our Services
          </div>
          <div class="mt-6 xl:mt-2 w-full text-lg">
            {{ service.content }}
          </div>
        </div>
      </div>
    </section>
    <section class="min-h-screen w-full bg-section p-16">
      <div class="inline-block">
        <div class="text-3xl font-bold capitalize text-orange">
          Our Area of Expertise
        </div>
        <div class="block py-1 divider-orange opacity-75"></div>
      </div>
      <div class="flex flex-row flex-wrap py-10">
        <div class="order-1 xl:w-1/6">
          <div class="w-16 md:w-32">
            <div
              class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
            >
              <img
                src="~/assets/images/training.svg"
                alt="IT software training"
                class="h-16 w-16 md:h-32 md:w-32 my-auto p-2 pb-4"
              />
            </div>
          </div>
        </div>
        <div class="order-2 xl:w-5/6 mb-12">
          <h1 class="text-2xl text-orange-600 font-semibold">IT Training</h1>
          <p class="xl:w-2/3 mt-2 text-white">
            {{ service.training }}
          </p>
        </div>
        <div class="order-4 xl:order-3 text-right mb-12 xl:mb-0 xl:w-5/6">
          <h1 class="text-2xl text-orange-600 font-semibold">
            Website Development and Design
          </h1>
          <p class="xl:w-2/3 ml-auto mt-2 text-white">
            {{ service.website }}
          </p>
        </div>
        <div class="order-3 xl:order-4 w-full xl:w-1/6 xl:mb-12">
          <div class="ml-auto w-16 md:w-32">
            <div
              class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-xl bg-gray-900 border border-orange-700"
            >
              <img
                src="~/assets/images/web-development.svg"
                alt="web development"
                class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pb-4"
              />
            </div>
          </div>
        </div>
        <div class="order-5 xl:w-1/6">
          <div class="w-16 md:w-32">
            <div
              class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-lg bg-gray-900 border border-orange-700"
            >
              <img
                src="~/assets/images/mobile-development.svg"
                alt="mobile development"
                class="h-16 w-16 md:h-32 md:w-32 my-auto p-2 pb-4"
              />
            </div>
          </div>
        </div>
        <div class="order-6 xl:w-5/6 mb-12">
          <h1 class="text-2xl text-orange-600 font-semibold">
            Mobile Application
          </h1>
          <p class="xl:w-2/3 mt-2 text-white">
            {{ service.mobile }}
          </p>
        </div>
        <div class="order-8 xl:order-7 text-right xl:w-5/6">
          <h1 class="text-2xl text-orange-600 font-semibold">
            IT Infrastructure and Hardware
          </h1>
          <p class="xl:w-2/3 ml-auto mt-2 text-white">
            {{ service.infrastructure }}
          </p>
        </div>
        <div class="order-7 xl:order-8 w-full xl:w-1/6">
          <div class="ml-auto w-16 md:w-32">
            <div
              class="h-16 w-16 md:h-32 md:w-32 rounded-full shadow-xl bg-gray-900 border border-orange-700"
            >
              <img
                src="~/assets/images/it_infrastructure.svg"
                alt="IT infrastructure"
                class="h-16 w-16 md:h-32 md:w-32 my-auto mx-auto pb-4"
              />
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const service = await $axios.$get('/our-services')

    return { service }
  },
  head() {
    return {
      title: this.service.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.service.meta_description,
        },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.service.meta_title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.service.meta_description,
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
          content: this.service.meta_title,
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.service.meta_title,
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.service.meta_description,
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
          content: this.service.meta_description,
        },
      ],
    }
  },
}
</script>
