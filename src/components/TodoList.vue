<template>
  <div>
    <ul class="todo-list" v-if="todoList.length">
      <TodoItem :list="todoList" />
    </ul>
    <div v-else class="todo-item-none">no data!</div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
import eventBus from '../utils/event-bus'

export default {
  name: 'TodoList',
  components: {
    TodoItem,
  },
  data() {
    return {
      todoList: [],
    }
  },
  created() {
    this.todoList = JSON.parse(localStorage.getItem('todoList')) || []
  },
  mounted() {
    eventBus.$on('addItem', this.handleAddItem)
  },
  methods: {
    handleAddItem(newItem) {
      if (!newItem) {
        alert('不能为空')
        return
      }
      this.todoList.push({
        todoContent: newItem,
        isFinished: false,
      })
    },
  },
  watch: {
    todoList: {
      deep: true,
      handler: function(to) {
        localStorage.setItem('todoList', JSON.stringify(to))
      },
    },
  },
}
</script>

<style scoped>
.todo-list {
  padding: 0;
}
.todo-item-none {
  margin-top: 40px;
  color: #999999;
  text-align: center;
}
</style>
