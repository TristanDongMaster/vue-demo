<template>
<form v-on:submit.prevent="$emit('add',newTodoText)">
    <label for="new-todo">Add a todo - new </label>
    <input v-model="newTodoText" id="new-todo" placeholder="E.g. Feed the cat">
    <button>Add</button>
</form>
</template>

<script>
/* eslint-disable */
export default {
    name: 'Add',
    data() {
        return {
            newTodoText: '',
        }
    },
}
</script>
