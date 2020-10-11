<template>
  <div id="app">
  <AddTodo @add-todo="addTodo"/>
  <Todos v-bind:todos="todos" @del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos';
import AddTodo from '../components/addTodo';
import axios from 'axios';

export default {
  name: "Home",
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [],
    }
  },
  methods: {
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(() => this.todos = this.todos.filter(todo => todo.id != id))
      .catch(err => console.log(err));
    },
    addTodo(newTodo){
      const {title, completed} = newTodo;

      axios.post('https://jsonplaceholder.typicode.com/todos', {title, completed})
      .then(res => this.todos = [...this.todos, res.data])
      .catch(err => console.log(err));
    
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.todos = res.data)
    .catch(err => console.log(err));

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
.btn{
  display: inline-block;
  border: none;
  background: purple;
  color: white;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #800080c9;
}

</style>
