<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">
        nuxt-fundamentals
      </h1>
      <h2 class="subtitle">
        My hunky-dory Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link
          v-for="post in posts"
          :key="post.id"
          :to="{ name: 'posts-id', params: { id: post.id } }"
          class="button--grey"
        >
          {{ post.title }}
        </nuxt-link>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head() {
    return {
      title: 'Home page',
      metas: [
        { name: 'twitter:title', content: 'Nuxt Fundamentals' },
        { name: 'twitter:description', content: ' vue is love <3' },
        { name: 'tiwtter:image', content: 'https://i.imgur.com/PzEm5j2.png' },
        { name: 'twitter:card', content: 'sumary_large_image' }
      ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style>
.container {
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
