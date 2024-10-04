<template>
    <section>
      <h2>Список задач</h2>
      <form @submit.prevent="addTask">
        <input type="text" placeholder="Введите новую задачу" v-model="newTask" required />
        <button type="submit">Добавить</button>
      </form>

      <TaskItem 
        v-for="task in renderTask" 
        :task="task" 
        :key="task.id"
        @del="deleteTask"
        @toggle="toggleCompletion"/>
      
    </section>
</template>

<script>
import TaskItem from './TaskItem.vue';
let id = 0;

export default {
    data() {
        return {
            tasks: [],
            newTask: ''
        };
    },
    components: {
        TaskItem,
    },
    computed: {
        renderTask() {
            return this.tasks;
        }
    },
    methods: {
        addTask() {
            if (this.newTask.trim()) {
                this.tasks.unshift({
                    id: id++,
                    text: this.newTask,
                    completed: false
                });
                this.newTask = '';
            }
        },
        deleteTask(id) {
            this.tasks = this.tasks.filter(task => task.id !== id);
        },
        toggleCompletion(task) {
            task.completed = !task.completed;
        }
    }
};
</script>

<style scoped>
button {
margin-left: 10px;
};

</style>