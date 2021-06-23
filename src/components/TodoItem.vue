<template>
  <div>
    <li
      class="todo-item"
      v-for="(item, index) in list"
      :key="index"
      :class="{ finish: item.isFinished }"
    >
      <!-- item content -->
      <div class="todo-content">
        <span>{{ index + 1 }}. </span>
        <span>{{ item.todoContent }}</span>
      </div>
      <!-- button  -->
      <div class="operation">
        <i class="fa fa-check" v-on:click.stop="completeTodoItem(item)"></i>
        <i class="fa fa-trash" v-on:click.stop="deleteTodoItem(index)"></i>
      </div>
    </li>
  </div>
</template>

<script>
import 'font-awesome/css/font-awesome.min.css'

export default {
  name: 'TodoItem',
  props: { list: Array, msg: String },
  methods: {
    // complete todo item
    completeTodoItem(item) {
      item.isFinished = true
    },
    // delete todo item
    deleteTodoItem(index) {
      this.list.splice(index, 1)
    },
  },
}
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  margin-bottom: 20px;
  border-radius: 12px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
}
.todo-item:hover {
  cursor: pointer;
  transform: scale(1.02);
}
.finish {
  text-decoration: line-through;
  font-style: italic;
  color: #999999;
}
.operation i:nth-child(1) {
  padding-right: 8px;
}
.operation i:hover {
  color: #7f95f7;
}
</style>
