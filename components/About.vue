<template>
  <section>
    <div class="bg-about px-20 xl:px-24 h-screen">
      <div class="flex flex-row flex-wrap text-white py-40">
        <div class="w-full xl:w-1/2">
          <div
            class="w-full text-4xl text-center xl:text-left font-semibold text-white mb-2"
          >
            About Us
          </div>
          <div class="mt-6 xl:mt-2 w-full text-lg">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum,
            suscipit in voluptates veniam iure natus ullam quos facilis soluta
            iusto quaerat nemo, quidem voluptate id temporibus eveniet quo aut
            veritatis deserunt libero dolore quis nesciunt! Labore praesentium
            nemo totam ratione?
          </div>
        </div>
        <div class="w-full xl:w-1/2">
          <img src="" alt="" class="mx-auto h-40" />
        </div>
      </div>
    </div>
  </section>
</template>
<style>
.bg-about {
  background: linear-gradient(
      to right,
      rgb(255, 255, 255, 0),
      rgba(0, 0, 0, 0.76)
    ),
    linear-gradient(rgba(0, 0, 0, 0.859), rgba(184, 83, 1, 0.645)),
    url('~assets/images/bg-about.jpg');
  background-size: cover;
  overflow: hidden;
}
</style>
