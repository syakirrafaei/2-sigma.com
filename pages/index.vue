<template>
  <div>
    <Hero :hero="hero" />
    <Services />
    <Clients :clients="clients" />
    <section id="contact"><Contact /></section>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const hero = await $axios.$get('/homepage')
    const clients = await $axios.$get('/client-logos')

    return { hero, clients }
  },
  head() {
    return {
      title: this.hero.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.hero.meta_description,
        },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.hero.meta_title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.hero.meta_description,
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
          content: this.hero.meta_title,
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.hero.meta_title,
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.hero.meta_description,
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
          content: this.hero.meta_description,
        },
      ],
    }
  },
}
</script>
