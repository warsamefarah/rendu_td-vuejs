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