<template>
  <div class="todo-card" :class="{'is-done':todo.completed}">
    <div class="content">
      <input type="checkbox" @change="markComplete">
      <h3 class="habit-title"> {{todo.title}} </h3>
    </div>
    <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    <!-- <div class="icons">
    <p class="iconify" data-icon="carbon:delete" data-inline="false" style="color: purple;"></p>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods:{
    markComplete(){
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
.todo-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 20px;
  padding: 5px 20px;
  border-radius: 20px;
  box-shadow: 0px 2px 5px rgb(207, 206, 206);
}

.habit-title {
  margin: 15px;
  color: rgba(0, 0, 0, 0.8);
}
.is-done{
  text-decoration: line-through;
}
.content {
  display: flex;
}
.del{
  border-radius: 50px;
  border: none;
  background-color: purple;
  color: white;
  width: 30px;
  height: 30px;
}
.icons{
  display: flex;
}

.iconify {
  padding: 5px;
}


</style>