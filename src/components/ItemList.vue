<template>
    <ul>
        <li v-for="(todo, index) in todolist" :key="index" :class="{underline: todo.checked}">
            {{todo.description}}
            <!-- {{todo.checked}} -->
            <RemoveButton @removeTodos="removeTodo(index)" />
            <CheckedButton @checkTodos="checkTodo(index)"/>
        </li>
    </ul>
</template>

<script>
import RemoveButton from './RemoveButton.vue';
import CheckedButton from './CheckButton.vue';

export default {
    name: 'ItemList',
    props: ['todolist'],
    emits: ['removeTodo', 'checkTodo'],
    components: {
        RemoveButton,
        CheckedButton
    },
    methods: {
        removeTodo(value) {
            this.$emit('removeTodo', value)
        },
        checkTodo(value) {
            this.$emit('checkTodo', value)
        }
    },
}
</script>

<style scoped>
    .underline {
        text-decoration: line-through;
    }
</style>