<template>
  <nav class="navbar">
    <div class="brand">
      <img
        class="logo"
        src="../assets/nuxt-logo.svg" >
      <h2>
        Nuxt Fudamentals
        <small>The wonderful vue world</small>
      </h2>
    </div>
    <div class="navigation">
      <a href="/">Home</a>
      <a href="/post">POST</a>
    </div>
  </nav>
</template>

<script>
export default {}
</script>
<style scoped>
.logo {
  height: 40px;
}
.brand {
  display: flex;
}
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: var(--secondary);
  padding: 30px;
}
h2 {
  font-size: 1.8em;
  text-transform: uppercase;
  padding: 0 40px;
  display: flex;
  flex-direction: column;
  color: var(--primary);
}
h2 small {
  font-size: 0.6em;
  text-transform: capitalize;
  color: #d9d9d9;
}
.navigation {
  display: flex;
  justify-content: center;
}
.navigation a {
  padding: 0 10px;
  color: #d9d9d9;
  text-transform: uppercase;
}
</style>
