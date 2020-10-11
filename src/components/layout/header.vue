<template>
  <header class="header">
    <h1 class="heading">TodoList</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "header"
}
</script>

<style scoped>
.header{
background-color: rgba(0, 0, 0, 0.97);
  color: #fff;
   padding: 20px;
  width: 100%;
  text-align: center;
}
.heading {
  font-size: 1.5em;
}
.header a{
  text-decoration: none;
}

</style>