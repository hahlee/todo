<template>
    <form @submit="addTodo" style="display: flex;">
        <input type="text" v-model="title" name="title" placeholder="Add Todo..." id="text">
        <button id="submit">ADD</button>
    </form>
</template>

<script>
// import uuid from 'uuid'
export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            }
            // send up to parent
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '@/styles/global.sass'

    form
        flex-flow: row nowrap
        justify-content: center
        align-items: center
        padding: 15px 0
        *
            font-size: 14px
        #text
            flex: 8
            padding: 10px
        #submit
            flex: 2
            margin-left: 10px
            @include btn
            &:hover
                background-color: darken($green, 10%)
</style>

