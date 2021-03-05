<template>
    <div class="list-body">
        <ul>
            <li v-for="task in tasks" :key="task.name">
                <input type="checkbox" v-if="task.status == true" checked><input type="checkbox" v-else> <p>{{task.name}}</p><button v-on:click="$emit('remover', task)">&Cross;</button>
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
    input[type=checkbox]:checked + p {
        text-decoration: line-through;
    }

    ul {
        width: 80%;
        margin: auto;
    }

    li {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    button {
        border: none;
        border-radius: 10px;
        background-color: #F14667;
        color: white;
        font-size: 1.5rem;
        cursor: pointer;
    }
</style>