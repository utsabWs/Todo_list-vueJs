<template>
    <div class="todo-list">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-6">
            <ul class="list-group">
              <li v-for="(task, index) in tasks" :key="index"
                  class="list-group-item d-flex justify-content-between align-items-center"
                  :class="{'task-added': task.isAdded}">
                {{ task.text }} <!-- Corrected 'task.test' to 'task.text' -->
                <button @click="deleteTask(index)" class="btn btn-danger">Delete</button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TodoList',
    props: {
      tasks: { // receives tasks as a prop from the parent
        type: Array,
        required: true
      }
    },
    methods: {
      deleteTask(index) { // Pass the index to the delete event
        this.$emit('delete-todo', index);
      }
    }
  };
  </script>
  