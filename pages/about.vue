<template>
  <div>
    <About />
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const service = await $axios.$get('/homepage')

    return { service }
  },
  head() {
    return {
      title: 'About Us',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.service.meta_description,
        },
      ],
    }
  },
}
</script>
