<template>
    <input placeholder="add todo" @input="handleOnChange" :value="todo" @keyup="handleOnKeyup"/>
    <button @click="addTodo">add</button>
</template>

<script>
export default {
    name: 'AddTodo',
    emits: ['addTodo'],
    data () {
        return {
            todo: ''
        }
    },
    methods: {
        addTodo() {
            if (this.todo.trim().length > 0) {
                this.$emit('addTodo', { description: this.todo, checked: false })
            }
            this.todo = ''
        },
        handleOnChange(e) {
            this.todo = e.target.value 
        },
        handleOnKeyup(e) {
            if (e.keyCode === 13) {
                this.addTodo()
            }
        }
    },
}
</script>

<style scoped>

</style>