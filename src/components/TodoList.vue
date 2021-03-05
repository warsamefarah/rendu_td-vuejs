<template>
    <div class="list-body">
        <ul>
            <li v-for="task in tasks" :key="task.name">
                <input type="checkbox" v-if="task.status == true" checked><input type="checkbox" v-else> <p>{{task.name}}</p>&Cross;
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'TodoList',
    props: ['tasks'],
    data() {
        return {
        }
    },
}
</script>

<style scoped>
    /* input[type=checkbox] */
    ul {
        width: 80%;
        margin: auto;
    }

    li {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }
</style>