<template>
    <div class="todo-list">
        <div v-for="todo in todos" v-bind:key="todo.id" class="todo-item-container">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped lang="sass">
    @import '@/styles/global.sass'

    .todo-item-container
        &:nth-child(odd)
            background-color: $lightGray
</style>