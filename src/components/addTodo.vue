<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add todo..." />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
  // import {v4 as uuid} from 'uuid';

  export default {
    name: "AddTodo",
    data() {
      return {
        title: ''
      }
    },
    methods: {
      addTodo(e) {
        e.preventDefault();
        const newTodo = {
          // id: uuid(),
          title: this.title,
          done: false
        }

        this.$emit('add-todo', newTodo);
        this.title = '';
      }
    }
  };
</script>

<style scoped>
  form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 7px;
     border-width: 0 0px 1px 0px;
  }
  input[type="submit"] {
    flex: 2;
    
  }
</style>

