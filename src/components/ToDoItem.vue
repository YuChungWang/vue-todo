<template>
  <li class="container">
    <p class="item-todo">{{ todoText }}</p>
    <button class="button-delete" v-on:click="handleDelButtonClick(todoText)">X</button>
  </li>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: {
    id: Number,
    todoText: String,
    handleDelButtonClick: Function
  },
}
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 300px;
  height: 60px;
  margin: 0 auto 8px;
  padding: 0 16px;
  border: 1px solid #2c3e50;
}

.item-todo {
  width: 262px;
  height: 30px;
  margin: 0;
  text-align: initial;
  line-height: 2;
}

.button-delete {
  width: 24px;
  height: 24px;
  border: none;
  border-radius: 6px;
  color: #ffffff;
  background: #d74153;
  cursor: pointer;
}
</style>
