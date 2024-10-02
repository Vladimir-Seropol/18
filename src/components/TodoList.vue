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

  
  export default {
  
    props: {
      tasks: {
        type: Array,
        default: () => []
      }
    },
    data() {
      return {
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
      }
  }
};



  </script>
  
  <style scoped>
 
  </style>