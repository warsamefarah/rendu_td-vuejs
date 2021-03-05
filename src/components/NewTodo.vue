<template>
    <div class="todo-body">
        <input v-model="task" placeholder="Nouvelle tâche">
        <input v-on:click="sendTask(task)" type="button" value="+">
    </div>
</template>

<script>
export default {
    name: 'NewTodo',
    data() {
        return {
            task: []
        }
    },
    methods: {
        sendTask(task) {
            this.$emit('newtask', task)
        }
    }
}
</script>

<style scoped>
    input {
        border: none;
        border-bottom: 1px solid grey;
        width: 200px;
    }

    input[type=button] {
        width: 50px;
        height: 50px;
        background-color: green;
        color: white;
        border: none;
        border-radius: 50px;
        font-size: 1.5rem;
    }
</style>