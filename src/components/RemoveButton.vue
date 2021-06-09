<template>
    <button @click="removeTodo">remove</button>
</template>

<script>
export default {
    emits: ['removeTodos'],
    methods: {
        removeTodo() {
            this.$emit('removeTodos')
        }
    },
}
</script>

<style scoped>

</style>