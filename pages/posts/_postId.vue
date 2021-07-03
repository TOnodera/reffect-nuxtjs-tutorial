<template>
    <div>
        <h1>記事個別ページ</h1>
        <h2>{{ post.title }}</h2>
        <p>{{ post.body }}</p>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    asyncData() {
        return {
            title: '個別ページ',
        };
    },
    head() {
        return {
            title: this.title,
        };
    },
    data() {
        return {
            post: {},
        };
    },
    async mounted() {
        const response = await axios.get(
            `https://jsonplaceholder.typicode.com/posts/${this.$route.params.postId}`
        );
        this.post = response.data;
    },
};
</script>
