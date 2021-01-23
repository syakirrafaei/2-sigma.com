<template>
  <div>
    <Services :clientsdata ="clientsdata"/>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {

    const clientsdata = await $axios.$get('/homepage')

    return { clientsdata }
  },
  head() {
    return {
      title: this.clientsdata.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.clientsdata.meta_description,
        },
      ],
    }
  },
}
</script>