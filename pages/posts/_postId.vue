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
    async asyncData(context) {
        const post = await context.$axios.$get(
            `https://jsonplaceholder.typicode.com/posts/${context.params.postId}`
        );
        return {
            post: post,
        };
    },
    head() {
        return {
            title: this.post.title,
        };
    },
};
</script>
