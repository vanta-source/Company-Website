<template>
<div class="Back-ground">
  <div class="todo-container">
    <h1>{{ title }}</h1>
    
    <!-- Input for adding a new task -->
    <div class="input-container">
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Add New" />
      <button @click="addTask">Add Task</button>
     
    </div>
    
    <!-- Displaying the task list -->
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
         <input class="checkbox" type="checkbox">
        <span>{{ task }}</span>
        <button @click="removeTask(index)">Delete</button>
        
      </li>
    </ul>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Untitle', // Title of the to-do list
      tasks: [], // List of tasks
      newTask: '', // New task input

    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim()) {
        this.tasks.push(this.newTask); // Add the new task to the list
        this.newTask = ''; // Clear the input field
      }
    },
    removeTask(index) {
      this.tasks.splice(index, 1); // Remove the selected task
    },
  },
};
</script>

<style scoped>
/* Styling for the to-do list page */
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,200..800;1,200..800&display=swap');

.Back-ground{
    height: 100vh;
    background-color: #344054;
    display: flex;
    
}
.todo-container {
  max-width: 600px;
  margin: 50px auto;
  padding: 20px 84px;
  background-color: #fff;
  border-radius: 8px;

}

.todo-container h1 {
  font-size: 2rem;
  margin-bottom: 20px;
  text-align: center;
  font-family: Plus Jakarta Sans;
}

.input-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
  
}

.input-container input {
  flex: 1;
  padding: 10px;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-right: 10px;
}

.input-container button {
  padding: 10px 20px;
  font-size: 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.input-container button:hover {
  background-color: #0056b3;
}

ul {
  list-style-type: none;
  padding: 0;
}

ul li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 0;
  border-bottom: 1px solid #ddd;
}

ul li button {
  background-color: #dc3545;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
}

ul li button:hover {
  background-color: #c82333;
}
</style>
