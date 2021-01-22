<template>
<Services :contacts ="contacts"/>
</template>
<script>
export default {
  async asyncData({ $axios }) {

    const contacts = await $axios.$get('/homepage')

    return { contacts }
  },
  head() {
    return {
      title: this.service.contacts,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.service.contacts_description,
        },
      ],
    }
  },
}
</script>