<template>
    <div>
      <h2>Список задач</h2>
      <form @submit.prevent="addTask">
        <input v-model="newTaskText" placeholder="Введите новую задачу" required />
        <button type="submit">Добавить</button>
      </form>
     
    </div>
  </template>
  
  <script>
  import TaskItem from './TaskItem.vue';
  
  export default {
  
    data() {
      return {
        tasks: [],
        newTaskText: '',
        nextId: 1
      };
    },
    methods: {
      addTask() {
        if (this.newTaskText.trim()) {
          const newTask = {
            id: this.nextId++,
            text: this.newTaskText,
            completed: false
          };
          this.tasks.push(newTask);
          this.newTaskText = '';
        }
      },
    }
  }
  </script>
  
  <style>
  /* Ваши стили для родительского компонента */
  </style>