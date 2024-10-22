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

<style scoped>
/* Styling for the welcome screen */
.welcome-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  text-align: center;
  background-color: #f0f0f0;
}

.welcome-container h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
}

.welcome-container h2 {
  font-size: 2rem;
  margin-bottom: 2rem;
}

.welcome-container button {
  padding: 10px 20px;
  font-size: 1.5rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.welcome-container button:hover {
  background-color: #0056b3;
}
</style>
