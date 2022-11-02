<template>
    <div>
        <h2 v-bind="$attrs">{{title}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'ArticleComp',
        props: {
            title: {
                type: String,
                required: true,
                default: 'Jeb'
            }
        },
        inheritAttrs: false
    }
</script>

<style scoped>

</style>