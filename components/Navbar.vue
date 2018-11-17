<template>
  <nav class="navbar">
    <nuxt-link
      :to="{ name: 'index' }"
      class="brand">
      <img
        class="logo"
        src="../assets/nuxt-logo.svg" >
      <h2>
        Nuxt Fudamentals
        <small>The wonderful vue world</small>
      </h2>
    </nuxt-link>
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
</style>
