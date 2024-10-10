<template>
    <ul>
        <li v-for="user in users">
            {{ user.name }}
        </li>
    </ul>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const users = ref();

await fetch("https://jsonplaceholder.typicode.com/comments")
    .then((res) => res.json())
    .then((json) => users.value = json);
</script>