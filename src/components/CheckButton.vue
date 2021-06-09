<template>
    <button @click="handleOnChecked">checked</button>
</template>

<script>
export default {
    methods: {
        handleOnChecked() {
            this.$emit('checkTodos')
        }
    },
}
</script>

<style scoped>

</style>