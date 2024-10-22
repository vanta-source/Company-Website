<template>
  <div id="app">
    <!-- Check if we are on the welcome screen or to-do list screen -->
    <div v-if="showWelcome">
      <!-- Welcome Screen -->
      <div class="welcome-container">
        <h1>Futuristic Todo List</h1>
        <h2>Start Smart</h2>
        <button @click="createTodoList">Create To-Do List</button>
      </div>
    </div>
    <div v-else>
      <!-- Todo List Screen -->
      <TodoList />
    </div>
  </div>
</template>
<script>
// Import the TodoList component (we will create this next)
import TodoList from './components/icons/TodoList.vue';

export default {
  data() {
    return {
      showWelcome: true, // Initially show the welcome screen
    };
  },
  methods: {
    createTodoList() {
      this.showWelcome = false; // Switch to the to-do list screen
    },
  },
  components: {
    TodoList,
  },
};
</script>

