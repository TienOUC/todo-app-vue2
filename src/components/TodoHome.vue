<template>
  <div class="todo-home">
    <h1>{{ msg }}</h1>
    <TodoAdd />
    <TodoList />
  </div>
</template>

<script>
import TodoAdd from './TodoAdd.vue'
import TodoList from './TodoList.vue'
export default {
  name: 'TodoHome',
  props: {
    msg: String,
  },
  components: {
    TodoAdd,
    TodoList,
  },
}
</script>

<style scoped>
.todo-home {
  padding: 40px 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: rgba(245, 246, 252);
  min-width: 400px;
  height: auto;
  border-radius: 24px;
  box-shadow: 0 5px 15px -5px rgba(0, 0, 0, 0.5);
}
</style>
