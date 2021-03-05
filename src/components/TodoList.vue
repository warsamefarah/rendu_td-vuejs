<template>
    <div class="list-body">
        <ul>
            <li v-for="task in tasks" :key="task.name">
                <input type="checkbox" value= {{task.status}}> {{task.name}}
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