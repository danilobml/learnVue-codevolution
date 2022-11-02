<template>
    <div>
        <h2>CompC: {{loggedUser}}</h2> 
    </div>
</template>

<script>
    export default {
        name: 'CompC',
        inject: ['loggedUser']
    }
</script>

<style scoped>

</style>