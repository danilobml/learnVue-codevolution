<template>
    <div>
        <form @submit.prevent="postReq">
            <label for="title">Title</label>
            <input type="text" name="title" id="title" v-model="postData.title">
            <label for="body">Body</label>
            <input type="text" name="body" id="body" v-model="postData.body">
            <label for="userId">User Id</label>
            <input type="number" name="userId" id="userId" v-model="postData.userId">
            <input type="submit" value="Submit">       
        </form>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        name: 'PostComp',
        data() {
            return {
                postData: {
                    title: '',
                    body: '',
                    userId: 0
                }
            }
        },
        methods: {
            postReq() {
                axios.post('https://jsonplaceholder.typicode.com/posts', this.postData)
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (error) {
                    console.log(error);
                });
            }
        }
    }
</script>

<style scoped>

</style>