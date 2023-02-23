<template>
    <div>
        <button @click="getPost">LOAD POSTS</button>
        <div v-for="post in posts" :key="post.id">
            <h3>{{ post.id }}{{ post.title }}</h3>
            <p>{{ post.body }}</p>
            <hr />
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: `post-list`,
    data() {
        return {
            posts: [],
        }
    },
    methods: {
        getPost() {
            axios
                .get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    console.log(response.data);
                    this.posts = response.data;
                })
                .catch((error) => {
                    console.log(error)
                })
        }
    }
}
</script>

<style scoped></style>