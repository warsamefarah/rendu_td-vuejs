<template>
    <div class="card">
        <header class="card-header">
            <div class="text-header">
                <p>{{date}}</p>
                <h1>Vue JS Tutorial ToDo List</h1>
                <p>{{ tasks.length }} tâches</p>
            </div>
        </header>
        <section>
            <NewTodo v-on:newtask="addTask($event)"></NewTodo>
            <TodoList v-bind:tasks="tasks" v-on:remover="removeTask($event)"></TodoList>
        </section>
    </div>
</template>

<script>
import NewTodo from './NewTodo.vue'
import TodoList from './TodoList.vue'

export default {
    name: 'TodoCard',
    data() {
        return {
            day: ['Lundi', 'Mardi', 'Mercredi', 'Jeudi', 'Vendredi', 'Samedi', 'Dimanche'],
            month: ['Janvier', 'Février', 'Mars', 'Avril', 'Mai', 'Juin', 'Juillet', 'Août', 'Septembre', 'Octobre', 'Novembre', 'Décembre'],
            tasks: []
        }
    },

    computed: {
        date: function () {
            const today = new Date()
            const currentdate = `${this.day[(today.getDay())]}` + ' ' + today.getDay() + ' ' + `${this.month[(today.getMonth())]}` + ' ' + today.getFullYear()
            return currentdate
        }
    },

    methods: {
        addTask (task_name) {
            const task = {
                name: task_name,
                status: false
            }
            this.tasks.push(task)
        },

        removeTask (task) {
            const index = this.tasks.indexOf(task)
            this.tasks.splice(index, 1)
        }
    },
    components: { NewTodo, TodoList },
}
</script>

<style scoped>
    .card {
        width: 80%;
        height: 600px;
        margin: auto;
        background-color: white;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    }

    .card-header {
        height: 10%;
        border-bottom: 1px solid gray;
    }

    .text-header {
        width: 80%;
        margin: auto;
        display: flex;
        justify-content: space-between;
    }
</style>