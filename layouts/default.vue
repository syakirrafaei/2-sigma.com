<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>

<style>
html {
  font-family: 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  overflow-x: hidden;
  background-color: black;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

body::-webkit-scrollbar {
  width: 0.5em;
}

body::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
}

body::-webkit-scrollbar-thumb {
  background-color: rgb(97, 36, 0);
  outline: 0px;
}

.text-orange {
  color: #bc5700;
}
.divider-orange {
  background: transparent
    radial-gradient(
      closest-side at 50% 50%,
      #dd8437 0%,
      #ba6a23 25%,
      #df7920 44%,
      #e07313 70%,
      #a0500a 85%,
      #5e2c00 100%
    )
    0% 0% no-repeat padding-box;
}
</style>
