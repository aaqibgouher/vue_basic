<template>
    <div>
        <div class="row">
            <div class="col-sm-6 offset-sm-3">
                <h2 class="mt-5">Todo App ({{ todos_count }})</h2>
                <TodoList :todos="todos"/>
                <br>
                <TodoAdd @saveTodoEvent="saveTodoData"/>
            </div>
        </div>
    </div>
</template>

<script>
import TodoList from './TodoList';
import TodoAdd from './TodoAdd';

export default {
    name: "TodoApp",
    components: {
        TodoList,
        TodoAdd
    },
    data() {
        return {
            todos: [
                {
                    title: "first todos"
                },
                {
                    title: "second todo"
                }
            ]
        }
    },
    methods: {
        saveTodoData(title){
            this.todos.push({
                title: title
            })
        }
    },
    computed: {
        todos_count(){
            return this.todos.length
        }
    }
}
</script>