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
    id: 'vuejs',
    posts: [
      {
        id: 'vuejs',
        title: 'what is vuejs ?',
        content:
          'Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable. The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects. On the other hand, Vue is also perfectly capable of powering sophisticated Single-Page Applications when used in combination with modern tooling and supporting libraries.'
      },
      {
        id: 'nuxtjs',
        title: 'What is nuxtjs ?',
        content: `Its main scope is UI rendering while abstracting away the client/server distribution. Our goal is to create a framework flexible enough that you can use it as a main project base or in addition to your current project based on Node.js. Nuxt.js presets all the configuration needed to make your development of a Vue.js Application Server Rendered more enjoyable. In addition, we also provide another deployment option called: nuxt generate. It will build a Static Generated Vue.js Application. We believe that option could be the next big step in the development of Web Applications with microservices. Furthermore, you can also use Nuxt.js to create single page applications (spa mode) quickly, useful to keep Nuxt features while working on backoffice applications. As a framework, Nuxt.js comes with a lot of features to help you in your development between the client side and the server side such as Asynchronous Data, Middleware, Layouts, etc.`
      },
      {
        id: 'vuex',
        title: 'what is vuex ?',
        content: `Vuex is a state management pattern + library for Vue.js applications. It serves as a centralized store for all the components in an application, with rules ensuring that the state can only be mutated in a predictable fashion. It also integrates with Vue's official devtools extension to provide advanced features such as zero-config time-travel debugging and state snapshot export / import.`
      },
      {
        id: 'nativescript-vue',
        title: 'wha is nativescript-vue ?',
        content: `NativeScript-Vue is a NativeScript plugin which allows you to use Vue.js to craft your mobile application. If you have used Vue.js before you will feel right at home with NativeScript-Vue.`
      }
    ]
  }),
  computed: {
    post() {
      return this.posts.find(post => post.id === this.id)
    },
    relatedPosts() {
      return this.posts.filter(post => post.id !== this.id)
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
