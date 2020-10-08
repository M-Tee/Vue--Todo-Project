<template>
  <div class="todo-card" :class="{'is-done':todo.done}">
    <div class="content">
      <h3 class="habit-title"> {{todo.title}} </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"]
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
}
.is-done{
  text-decoration: line-through;
}

.content {
  display: flex;
}

</style>