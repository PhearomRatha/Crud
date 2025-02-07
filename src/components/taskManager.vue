<template>
    <div>
      <ul>
        <li v-for="task in tasks" :key="task.name">
          <span>
            name task: {{ task.name }}  status: {{ task.status }}
          </span>
          <button @click="markCompleted(task.name)">Completed</button>
          <button @click="deleteTask(task.name)">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      tasks: {
        type: Array,
        required: true,
      },
    },
    emits: ['taskCompleted', 'deleteTask'],
    methods: {
      markCompleted(taskName) {
        this.$emit('taskCompleted', taskName);
      },
      deleteTask(taskName) {
        this.$emit('deleteTask', taskName);
      },
    },
  };
  </script>
  
  <style>
  </style>
  