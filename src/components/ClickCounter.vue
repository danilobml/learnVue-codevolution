<template>
    <div>
        <button @click="incrementCounter">Clicked {{count}} times</button>
    </div>
</template>

<script>
    // import CounterMixin from '../mixins/counter.js'   
    import useCounter from '@/composables/useCounter';
    export default {
        name: 'ClickCounter',
        setup() {
            const { count, incrementCounter} = useCounter(100, 5)

            return {
                count, incrementCounter
            }
        }
        // mixins: [CounterMixin]
    }
</script>

<style scoped>

</style>