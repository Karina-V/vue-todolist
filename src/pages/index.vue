<template>

    <div class=" mx-auto w-3/4 max-w-screen-sm">
        <div class="bg-slate-200 rounded-lg ">
            <Heading />
            <ReceivingList @create-todo="createTodo" />
            <TodoList :todo-items="todos" @remove="removeTodo" @todo-changed="onTodoChanged" />
        </div>
    </div>

</template>

<script>

import Heading from "../components/Heading/Heading.vue";
import ReceivingList from "../components/ReceivingList/ReceivingList.vue";
import TodoList from "../components/TodoList/TodoList.vue";


export default {
    components: {
        Heading,
        ReceivingList,
        TodoList,
    },

    data() {
        return {
            todos: [{ id: 1657721455206, text: "sss", done: false }],
        }
    },

    mounted() {
        if (localStorage.getItem("todos")) {
            this.todos = JSON.parse(localStorage.getItem("todos"));
        };
    },

    methods: {

        saveState() {
            localStorage.setItem("todos", JSON.stringify(this.todos));
        },

        onTodoChanged(todo) {
            const foundTodoIndex = this.todos.findIndex(t => t.id === todo.id)

            if (foundTodoIndex !== -1) {
                this.todos.splice(foundTodoIndex, 1, todo);
            } else {
                console.error("Error! Not found changed todo!!!");
            }

            this.saveState()
        },

        createTodo(todoText) {
            if (todoText.length > 0) {
                this.todos.push({ id: Date.now(), text: todoText, done: false });
            }

            this.saveState()
        },

        removeTodo(todo) {
            this.todos = this.todos.filter(t => t.id !== todo.id);
            this.saveState()
        },
    }
}
</script>
