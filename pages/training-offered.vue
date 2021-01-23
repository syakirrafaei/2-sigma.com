<template>
  <div>
    <Services :traindata ="traindata"/>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {

    const traindata = await $axios.$get('/homepage')

    return { traindata }
  },
  head() {
    return {
      title: this.traindata.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.traindata.meta_description,
        },
      ],
    }
  },
}
</script>