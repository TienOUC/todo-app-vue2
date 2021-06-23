<template>
  <div class="todo-add">
    <!-- 输入框和按钮 -->
    <input type="text" v-model.trim="newItem" @keyup.enter="addNewItem" />
    <button @click="addNewItem">
      <i class="btn-plus"></i>
    </button>
  </div>
</template>

<script>
import eventBus from '../utils/event-bus'
export default {
  name: 'TodoAdd',
  props: {},
  data() {
    return { newItem: '' }
  },
  methods: {
    addNewItem() {
      eventBus.$emit('addItem', this.newItem)
      this.newItem = ''
    },
  },
}
</script>

<style scoped>
.todo-add {
  position: relative;
  display: flex;
  align-items: center;
  margin: 20px 0;
}

.todo-add input {
  padding: 13px 52px 13px 18px;
  border-radius: 12px;
  border: none;
  outline: none;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.08);
  width: 100%;
  font-size: 1rem;
  color: #626262;
}

.todo-add button {
  width: 43px;
  height: 43px;
  border-radius: 12px;
  background: linear-gradient(#c0a5f3, #7f95f7);
  border: none;
  outline: none;

  color: white;
  position: absolute;
  right: 0px;

  cursor: pointer;
}

.todo-add .btn-plus {
  display: block;
  width: 100%;
  height: 100%;
  background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
  background-size: 50% 2px, 2px 50%;
  background-position: center;
  background-repeat: no-repeat;
}
</style>
