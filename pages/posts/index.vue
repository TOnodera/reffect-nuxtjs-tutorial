<template>
    <div>
        <h1>記事一覧</h1>
        <ul>
            <li v-for="post in posts" :key="post.id">
                <nuxt-link :to="'/posts/' + post.id">{{
                    post.title
                }}</nuxt-link>
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    async asyncData(context) {
        const posts = await context.$axios.$get(
            'https://jsonplaceholder.typicode.com/posts'
        );
        return {
            posts: posts,
        };
    },
};
</script>
