<template>
    <div class="todo-body">
        <input v-model="task" placeholder="Nouvelle tâche">
        <input v-on:click="sendTask" type="button" value="+">
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
            this.$emit('newTask', task)
        }
    }
}
</script>