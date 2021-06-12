<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<style>
html {
  height: 100vh;
  background: #000;
}

body {
  height: 500vh;
}

#nav {
  z-index: 1;
}
</style>
