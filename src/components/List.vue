<template>
<div id="todo-list-example">
    <Add v-on:add="addNewTodo" />
    <ul>
        <li is="item" v-for="(todo, index) in todos" v-bind:key="todo.id" v-bind:title="todo.title" v-on:remove="todos.splice(index, 1)"></li>
    </ul>
</div>
</template>

<script>
/* eslint-disable */
import Item from './Item.vue'
import Add from './Add.vue'

export default {
    components: {
        Item,
        Add
    },
    name: 'List',
    props: {
        todos: Array
    },
    data() {
        return {
            newTodoText: '',
            nextTodoId: 4
        }
    },
    methods: {
        addNewTodo: function (value) {
            this.todos.push({
                id: this.nextTodoId++,
                title: this.newTodoText || value
            })
            this.newTodoText = ''
        }
    }
}
</script>
