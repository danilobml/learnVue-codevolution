<template>
    <div>
        <button @click="getPosts">Load Posts</button>
        <h3 v-if="errorMsg">{{errorMsg}}</h3>
        <div v-for="post in posts" :key="post.id">
            <h3>{{post.id}} - {{post.title}}</h3>
            <p>{{post.body}}</p>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        name: 'PostList',
        data() {
            return {
                posts: [],
                errorMsg: ""
            }
        },
        methods: {
            getPosts() {
                axios.get('https://jsonplaceholder.typicode.com/posts')
                    .then((response)=> this.posts = response.data)
                    .catch((error)=> {
                        this.errorMessage = error.message
                    })
            }
        }
    }
</script>

<style scoped>

</style>