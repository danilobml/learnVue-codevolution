<template>
    <div>
        <ul>
            <li v-for="name in names" :key="name.firstName">
                <slot :firstName="name.firstName" :lastName="name.lastName"></slot>    
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'NameList',
        data(){
            return {
                names: [
                    {
                        firstName: 'Jeb',
                        lastName: 'Jones'
                    },
                    {
                        firstName: 'Job',
                        lastName: 'Janes'
                    },
                    {
                        firstName: 'Jib',
                        lastName: 'Junes'
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>