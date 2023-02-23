<template>
    <div>
        <form @submit.prevent="createPost">
            <div>
                <label for="userId">Post User Id</label>
                <input type="text" id="userId" v-model="FormData.userId">
            </div>
            <div>
                <label for="title">Post title</label>
                <input type="text" id="title" v-model="FormData.title">
            </div>
            <div>
                <label for="body">Post body</label>
                <input type="text" id="body" v-model="FormData.body">
            </div>
            <button>Create post</button>
        </form>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: `Create-post`,
    data() {
        return {
            FormData: {
                userId: '',
                title: '',
            }
        }
    },
    methods: {
        createPost() {
            axios.post('https://jsonplaceholder.typicode.com/posts', this.FormData)
                .then((response) => {
                    console.log(response.data);
                })
                .catch((error) => {
                    console.error(error);
                })
        }
    }
}
</script>

<style scoped></style>