<template>
  <div id="app">
    <TodoInput @add-todo="addTodo"/>
    <TodoList :tasks="tasks" @delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import TodoInput from './components/todoInput.vue';
import TodoList from './components/todoList.vue';

export default {
  name: 'App',
  components: {
    TodoInput, // Registering the TodoInput component
    TodoList   // Registering the TodoList component
  },
  data() {
    return {
      tasks: []  // Initialize tasks array
    };
  },
  methods: {
    addTodo(newTask) {
      const task = {
        text: newTask, // Store task text
        isAdded: false  // Mark task as not added yet
      };

      setTimeout(() => {
        task.isAdded = true; // Mark the task as added after the delay
      }, 100);

      this.tasks.push(task); // Add the new task to the tasks array
    },
    deleteTodo(index) {
      this.tasks.splice(index, 1); // Delete the task at the given index
    }
  }
};
</script>

<style>
#app {
  background-color: white; 
}
</style>
