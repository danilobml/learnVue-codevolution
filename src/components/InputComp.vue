<template>
    <div>
        <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)">
    </div>
</template>

<script>
    export default {
        name: 'InputComp',
        props: {
            modelValue: String
        }
    }
</script>

<style scoped>
    input[type="text"] {
        width: 300px;
        height: 30px;
        font-size: 25px;
    }
</style>