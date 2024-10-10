<script setup lang="ts">
import MouseTracker from "./components/MouseTracker.vue";
import ApiComponent from "./components/ApiComponent.vue";
import AsyncComponent from "./components/AsyncComponent.vue";
</script>

<template>
    <Suspense>
        <AsyncComponent />

        <template #fallback>
            Loading...
        </template>
    </Suspense>
</template>
