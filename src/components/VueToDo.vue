<template>
  <div class="vue-to-do">
    <h1>{{ msg }}</h1>
    <input v-model="newTodo" class="input-add" placeholder="add todo.." />
    <button class="button-add" v-on:click="handleAddButtonClick">Add</button>
    <ul class="todo-item-section">
      <ToDoItem v-for="todo in todoList" :key="todo.id" :todoText="todo.text" :handleDelButtonClick="handleDelButtonClick"/>
    </ul>
  </div>
</template>

<script>
import ToDoItem from './ToDoItem'

export default {
  name: 'VueToDo',
  props: {
    msg: String
  },
  components: {
    ToDoItem
  },
  data: () => {
    return {
      newTodo: '',
      count: 3,
      todoList: [
        {id: 0, text: 'Learning Vue'},
        {id: 1, text: 'Lingoda Sprint'},
        {id: 2, text: 'Final Fantasy VII Remake'}
      ]
    }
  },
  methods: {
    handleAddButtonClick: function() {
      this.todoList.push({id: this.count++ , text: this.newTodo})
      this.newTodo = ''
    },
    handleDelButtonClick: function(todoText) {
      const index = this.todoList.map(item => item.text).indexOf(todoText)
      this.todoList.splice(index, 1)
    }
  }
}
</script>

<style scoped>
.input-add {
  width: 170px;
  height: 30px;
  padding: 0 8px;
  margin-right: 8px;
  box-sizing: border-box;
  outline: none;
}

.button-add {
  width: 72px;
  height: 30px;
  border: none;
  border-radius: 6px;
  background: #41b883;
  cursor: pointer;
}

.todo-item-section {
  margin-top: 36px;
  padding: 0;
}

</style>
