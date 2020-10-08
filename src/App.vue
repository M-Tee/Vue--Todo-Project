<template>
  <div id="app">
  <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from './components/Todos'

export default {
  name: "App",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Meditate",
          done: true,
        },
        {
          id: 2,
          title: "Read",
          done: false,
        },
        {
          id: 3,
          title: "workout",
          done: false,
        },
      ],
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>
