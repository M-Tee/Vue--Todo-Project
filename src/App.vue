<template>
  <div id="app">
  <Header/>
  <Todos v-bind:todos="todos" @del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/layout/header'
import Todos from './components/Todos'

export default {
  name: "App",
  components: {
    Header,
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
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }
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
