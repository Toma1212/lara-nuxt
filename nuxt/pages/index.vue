<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="container">
        <div>
          <logo />
          <h1 class="title">
            {{data}}
          </h1>
          <h2 class="subtitle">
            My superb Nuxt.js project
          </h2>
          <div class="links">
            <a
              href="https://nuxtjs.org/"
              target="_blank"
              class="button--green"
            >
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
    </v-flex>
  </v-layout>
</template>
<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  async asyncData(app) {
    const data = await app.$axios.$get('/api')
    return {
      data
    }
  }
}
</script>
