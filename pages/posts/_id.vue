<template>
  <div class="post">
    <article class="content">
      <header class="header">
        <h1>{{ post.title }}</h1>
      </header>
      <p>{{ post.content }}</p>
    </article>
    <aside>
      <h3>Posts you might enjoy</h3>
      <ul>
        <li
          v-for="related in relatedPosts"
          :key="related.id">
          <nuxt-link :to="{ name: 'posts-id', params: { id: related.id } }">{{ related.title }}</nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>
<script>
export default {
  data: () => ({
    id: 'vuejs'
  }),
  head() {
    return {
      title: this.post.title,
      metas: [
        { name: 'twitter:title', content: this.post.title },
        { name: 'twitter:description', content: this.post.content },
        { name: 'tiwtter:image', content: 'https://i.imgur.com/PzEm5j2.png' },
        { name: 'twitter:card', content: 'sumary_large_image' }
      ]
    }
  },
  computed: {
    post() {
      return this.$store.state.posts.all.find(post => post.id === this.id)
    },
    relatedPosts() {
      return this.$store.state.posts.all.filter(post => post.id !== this.id)
    }
  },
  mounted() {
    this.id = this.$route.params.id
  }
}
</script>

<style>
.post {
  background: var(--dark);
  height: 100vh;
  overflow: hidden;
  display: flex;
  justify-content: space-between;
}
.header h1 {
  padding: 10px 0;
  color: var(--primary);
  text-transform: uppercase;
}

.content {
  margin-top: 50px;
  color: var(--white);
  padding: 40px;
  width: 80vw;
  font-size: 1.2em;
}
aside {
  margin-top: 50px;
  padding: 40px;
  width: 20vw;
}
aside h3 {
  color: var(--accent);
  text-transform: uppercase;
}
aside ul li {
  color: var(--primary);
}
aside ul li a {
  color: white;
}
</style>
