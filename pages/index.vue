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
      ],
    }
  },
}
</script>
