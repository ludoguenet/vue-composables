<script setup lang="ts">
import {ref} from 'vue';
import {useFetch} from '../composables/fetch.ts'

const url = ref('https://jsonplaceholder.typicode.com/albums');

const { data, error } = useFetch(() => url.value);

const loadComments = function () {
    url.value = 'https://jsonplaceholder.typicode.com/comments';
}

const loadUsers = function () {
    url.value = 'https://jsonplaceholder.typicode.com/users';
}
</script>

<template>
    <button @click.prevent="loadComments">Charger les commentaires</button>
    <button @click.prevent="loadUsers">Charger les utilisateurs</button>

    <div v-if="error">Oops! Error encountered: {{ error.message }}</div>
    <div v-else-if="data">
        Data loaded:
        <pre>{{ data }}</pre>
    </div>
    <div v-else>Loading...</div>
</template>