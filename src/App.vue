<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/CardDetailPage">About</router-link> |
  </div>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: freeform-serifs;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
  background-color: black;
}
#nav {
  display: none;
}
</style>
