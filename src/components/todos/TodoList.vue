<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item" v-for="todo in todos" :key="todo.title">{{ todo.title }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "TodoList",
    props: [ "todos" ],
    data() {
        return {

        }
    }
}
</script>