<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/layout/header';

export default {
  name: "app",
  components: {
    Header
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
  padding-top: 20px;
}

#nav a {
  font-weight: bold;
  color: #ffffffad;
}

#nav a.router-link-exact-active {
  color: #fff;
}
</style>
