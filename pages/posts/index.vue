<template>
    <div>
        <h1>記事一覧</h1>
        <ul>
            <li v-for="post in posts" :key="post.id">
                {{ post.title }}
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    async asyncData() {
        const response = await axios.get(
            'https://jsonplaceholder.typicode.com/posts'
        );
        return {
            posts: response.data,
        };
    },
};
</script>
