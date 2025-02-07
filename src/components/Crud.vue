<template>
    <div class="task-manager">
      <div class="input-section">
        <input type="text" v-model="taskname" placeholder="Enter a task" />
        <button type="button" @click="addItem">{{ editTaskId ? 'Save Task' : 'Add Task' }}</button>
      </div>
  
      <div class="search-section">
        <input v-model="searchQuery" type="text" placeholder="Search tasks..." />
      </div>
  
      <div class="task-list">
        <div v-for="task in filteredItems" :key="task.id" class="task-item">
          <p class="task-text">{{ task.name }}</p>
          <div class="task-buttons">
            <button class="btn-delete" @click="deleteEvent(task)">Delete</button>
            <button class="btn-edit" @click="editTask(task)">Edit</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        taskname: '',
        tasks: [],
        editTaskId: null,
        searchQuery: ''
      };
    },
    methods: {
      addItem() {
        if (this.taskname.trim().length > 0) {
          if (this.editTaskId !== null) {
            const task = this.tasks.find(t => t.id === this.editTaskId);
            if (task) task.name = this.taskname;
            this.editTaskId = null;
          } else {
            this.tasks.push({
              name: this.taskname
            });
          }
          this.taskname = '';
        }
      },
      deleteEvent(task) {
        const index = this.tasks.findIndex(t => t.id === task.id);
        if (index !== -1) {
          this.tasks.splice(index, 1);
        }
      },
      editTask(task) {
        this.taskname = task.name;
        this.editTaskId = task.id;
      }
    },
    computed: {
      filteredItems() {
        return this.tasks.filter(item =>
          item.name.toLowerCase().includes(this.searchQuery.toLowerCase())
        );
      }
    }
  };
  </script>
  
  <style scoped>
  .task-manager {
    font-family: Arial, sans-serif;
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background-color: #fff;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .input-section,
  .search-section {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
  }
  
  input[type="text"] {
    flex: 1;
    padding: 8px;
    margin-right: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  button {
    padding: 8px 12px;
    background-color: green;
    cursor: pointer;
    border: none;
    border-radius: 4px;
    font-weight: bold;
  }
  
  button:hover {
    opacity: 0.85;
  }
  
  .btn-delete {
    background-color: #e74c3c;
    margin-right: 10px;
  }
  
  .btn-edit {
    background-color: #3498db;
  }
  
  .task-list {
    margin-top: 20px;
  }
  
  .task-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 12px;
    border: 1px solid #ddd;
    border-radius: 8px;
    margin-bottom: 10px;
    background-color: #f9f9f9;
    transition: transform 0.2s ease;
    color: black;
  }
  
  .task-item:hover {
    transform: scale(1.02);
  }
  
  .task-text {
    margin: 0;
    font-weight: 500;
  }
  
  .task-buttons {
    display: flex;
    gap: 10px;
  }
  </style>