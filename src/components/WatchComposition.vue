<template>
    <div>
        <label for="composition-watch">Composition Watcher:</label>
        <input type="text" id="composition-watch" v-model="compName">
    </div>
</template>

<script>
    import { ref, watch } from 'vue'
    export default {
        name: 'WatchComposition',
        setup() {
            const compName = ref('')

            watch(compName, (newValue, oldValue)=> {
                console.log(newValue, oldValue)
            })  

            return {
                compName
            }
        }  
    }
</script>

<style scoped>

</style>