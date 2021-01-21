<template>
  <div>
    <Hero :hero="hero" />
    <Services />
    <Clients />
    <Contact />
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const hero = await $axios.$get('/homepage')

    return { hero }
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
