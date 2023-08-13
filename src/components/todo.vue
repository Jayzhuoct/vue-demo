<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "todo"
})
</script>

<template>
  <div>
    <h2>待办事项列表</h2>
    <input v-model="newTodo" placeholder="添加待办事项">
    <button @click="addTodo">添加</button>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="removeTodo(index)">删除</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: '',
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo);
        this.newTodo = '';
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>


<style scoped>

</style>