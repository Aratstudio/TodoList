<template>
    <div>
    <ul>
       <TodoItem v-for="(todo, i) in todos" v-bind:todo="todo" v-bind:index="i" v-on:remove-todo="removeTodo"/>
    </ul>
    </div>
</template>

<script>
import TodoItem from "@/components/TodoItem"
export default {
    props: ['todos'],
    components: {
        TodoItem
    },
    methods: {
        removeTodo(id) {
            console.log(id)
            this.$emit('remove-todo', id)
        }
    },
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin-top:2.6rem;
        padding: 0;
        margin: 0;
    }
</style>


