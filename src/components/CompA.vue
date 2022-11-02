<template>
    <div>
        <h2>CompA</h2>
        <CompB />
    </div>
</template>

<script>
import CompB from './CompB.vue';

    export default {
        name: 'CompA',
        components: {
            CompB
        }
    }
</script>

<style scoped>

</style>