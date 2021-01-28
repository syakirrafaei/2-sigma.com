<template>
  <div>
    <About :content="about.content" />
    <!-- put some error here and comments -->
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const about = await $axios.$get('/about')

    return { about }
  },
  head() {
    return {
      title: this.about.meta_title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: this.about.meta_description,
        },
      ],
    }
  },
}
</script>
