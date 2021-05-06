<template>
  <div id="app">
    <section class="text-center">
      <h1 class="mt-2"><b>Store App Mevn</b></h1>
      <div id="nav">
        <router-link to="/">Inicio</router-link> |
        <router-link to="/about">Tienda</router-link>
      </div>
    </section>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding: 5px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
.c-poiner{
  cursor: pointer;
}
</style>
