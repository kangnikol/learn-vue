<template>
    <div class="p-4 bg-base text-text">
        <div v-for="user in users.data" :key="user.id">
            <div
                class="p-4 border-4 border-blue my-4 rounded-md shadow-2xl shadow-pink hover:bg-blue hover:text-base hover:shadow-blue hover:border-pink">
                <p>{{ user.name }} ({{ user.username }})</p>
            </div>
            <div v-for="(address, i) in user.company" :key="i">
                <p>{{ address.name }}</p>
            </div>
        </div>
        <div v-for="post in posts.data" :key="post.id">
            <div
                class="p-4 border-4 border-pink my-4 rounded-md shadow-2xl shadow-blue hover:bg-pink hover:text-base hover:shadow-pink hover:border-blue">
                <p>{{ post.title }}</p>
            </div>
        </div>
    </div>
</template>
<script>
import axios from 'axios'

export default {
    async setup() {
        const [users, posts] = await Promise.all([
            axios.get('https://jsonplaceholder.typicode.com/users'),
            axios.get('https://jsonplaceholder.typicode.com/posts')
        ]);
        return { users, posts };
    },
}
</script>
<style></style>