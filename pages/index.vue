<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        mock-ky-cypress
      </h1>
      <h2 class="subtitle">
        My magnificent Nuxt.js project
      </h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  async mounted() {
    const ky = require('ky').default
    const res = await ky('https://jsonplaceholder.typicode.com/posts/1').json()
    const res2 = await ky('https://jsonplaceholder.typicode.com/posts/2').json()
    console.log(res)
    console.log(res2)
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
