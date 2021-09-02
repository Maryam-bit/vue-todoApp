<template>
  <div class="todo-container">
    <form @submit.prevent="addTodo">
      <input
        class="todo-input"
        type="text"
        id="text"
        name="text"
        v-model="newTodo"
        placeholder="Add todo"
        required
      />
      <button type="submit" v-on:keyup.enter="addTodo">
        <i class="fa fa-plus"></i>
      </button>
      <button type="button" @click="allDone">
        <i class="fa fa-check"></i>
      </button>
      <button type="button" @click="allDelete">
        <i class="fa fa-trash"></i>
      </button>
    </form>

    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        <input type="checkbox" v-model="todo.done" />
        <span :class="{ done: todo.done }">{{ todo.title }}</span>
        <button class="delete-btn" @click="deleteTodo(todo)">
          <i class="fa fa-trash delete-todo"></i>
        </button>
      </li>
    </ul>
  </div>
</template>


<script>
export default {
  name: "Todo",
  data() {
    return {
      name: "hello",
      newTodo: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length) {
        this.todos.push({
          title: this.newTodo,
          done: false,
        });
      }
      this.newTodo = "";
    },
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    allDone() {
      this.todos.forEach((todo) => {
        todo.done = true;
      });
    },
    allDelete() {
      this.todos.splice(0, this.todos.length);
    },
  },
};
</script>


<style scoped src="../assets/style.css"></style>