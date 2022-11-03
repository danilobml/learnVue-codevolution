<template>
    <div>
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="firstName">
        <h2>Composition: {{cFirstName}}</h2>
        <h2>{{greet}}</h2>
        <h2>Computed Name: {{computedValue}}</h2>
        <h2>Refs: This is {{firstName}} {{lastName}}, the {{heroName}}</h2>
    </div>
</template>

<script>
    import { ref, reactive, computed, toRefs } from 'vue'
    export default {
        name: 'DataComp',
        setup() {
            const cFirstName = ref('Clark')
            // const cLastName = ref('Kent')

            const state = reactive({
                firstName:'Clark',
                lastName: 'Kent',
                heroName: 'Superman'
            })

            const computedValue = computed(function() {
                return state.firstName + state.lastName
            })

            const greet = `Hello, ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`

            return {
                cFirstName,
                greet,
                ...toRefs(state),
                computedValue
            }
        },
  
    }
</script>

<style scoped>

</style>