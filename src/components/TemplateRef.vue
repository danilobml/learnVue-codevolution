<template>
    <div>
        <label for="temp-ref-input">Template Ref:</label>
        <input type="text" id="temp-ref-input" ref="inputRef">
    </div>
</template>

<script>
    export default {
        name: 'TemplateRef',
        mounted() {
            this.$refs.inputRef.focus()
        }
    }
</script>

<style scoped>

</style>