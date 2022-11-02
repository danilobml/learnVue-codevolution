<template>
    <h2>Oi {{name}}, seu {{position}}!</h2>
</template>

<script>
    export default {
        name: 'GreetComp',
        props: ['name', 'position']
    }
</script>

<style>

</style>