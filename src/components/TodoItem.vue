<template>
    <div class="todo-item" :class="{'is-complete':todo.completed}">
        <p>{{todo.title}}</p>
        <button class="mark-complete" @click="markComplete"><span></span></button>
        <button @click="$emit('del-todo', todo.id)" class="del">DELETE</button>    
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped lang="sass">
    @import '@/styles/global.sass'

    .todo-item
        display: flex
        flex-flow: row nowrap
        align-items: center
        justify-content: space-between
        padding: 10px
        border-bottom: 1px $darkGray dotted
        &.is-complete 
            p 
                text-decoration: line-through
            .mark-complete span:after
                content: "Undo"
        .mark-complete span:after
            content: "Complete Task"
        p
            display: inline-block
            margin: 0 1em
            max-width: 350px
        .mark-complete
            @include btn
            background-color: $blue
            width: 110px
            margin-left: auto
            &:hover
                background-color: darken($blue, 10%)
        .del
            @include btn
            background-color: $red
            margin-left: 8px
            &:hover
                background-color: darken($red, 10%)
</style>