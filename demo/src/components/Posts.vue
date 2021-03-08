<template>
    <div class="container">

    <table class="table table-dark table-striped">
    <thead>
        <tr>
        <th scope="col">#ID</th>
        <th scope="col">Title</th>
        <th scope="col">Body</th>
        </tr>
    </thead>
    <tbody>
        <tr v-for="post in posts" :key="post.id">
        <td>{{ post.id }}</td>
        <td>{{ post.title }}</td>
        <td>{{ post.body }}</td>
        </tr>
    </tbody>
    </table>

    <table class="table table-dark table-striped caption-top">
    <caption>HTTP Data via REST API</caption>
    <thead>
        <tr>
        <th scope="col">#ID</th>
        <th scope="col">UserId</th>
        <th scope="col">Title</th>
        <th scope="col">Body</th>
        </tr>
    </thead>
    <tbody>
        <tr v-for="hPost in httpPosts" :key="hPost.id">
        <td>{{ hPost.id }}</td>
        <td>{{ hPost.userId }}</td>
        <td>{{ hPost.title }}</td>
        <td>{{ hPost.body }}</td>
        </tr>
    </tbody>
    </table>

    </div>
</template>

<script>

import axios from 'axios';

export default {
    name: 'PostsExample',
    data(){
        return{
            posts: [
                {id: 1, title: 'Post 1', body: 'This is Post 1'},
                {id: 2, title: 'Post 2', body: 'This is Post 2'},
                {id: 3, title: 'Post 3', body: 'This is Post 3'},
                {id: 4, title: 'Post 4', body: 'This is Post 4'},
                {id: 5, title: 'Post 5', body: 'This is Post 5'},
                {id: 6, title: 'Post 6', body: 'This is Post 6'}
            ],
            httpPosts: []
        }
    },

    created(){
        console.log('lifecycle created');

        axios.get('https://jsonplaceholder.typicode.com/posts').then(httpPosts=>{
            this.httpPosts = httpPosts.data;
        });
    }
}
</script>

<style>

</style>