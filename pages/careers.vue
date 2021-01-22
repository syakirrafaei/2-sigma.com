<template>
  <div>
    <Services :service ="service"/>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {

    const careerdata = await $axios.$get('/homepage')

    return { careerdata }
  },
  head() {
    return {
      title: this.careerdata.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.careerdata.meta_description,
        },
      ],
    }
  },
}
</script>