<template>
  <div class="post">
    <header class="header">
      <h1>What is VueJS ?</h1>
    </header>
    <article class="content">Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. Unlike other monolithic frameworks, Vue is designed from the ground up to be incrementally adoptable. The core library is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects. On the other hand, Vue is also perfectly capable of powering sophisticated Single-Page Applications when used in combination with modern tooling and supporting libraries.</article>
  </div>
</template>
<style>
.post {
  background: var(--dark);
  height: 100vh;
  overflow: hidden;
}
.header {
  margin-top: 50px;
  padding: 0 40px;
}
.header h1 {
  color: var(--primary);
  text-transform: uppercase;
}

.content {
  color: var(--white);
  padding: 40px;
  font-size: 1.2em;
}
</style>
