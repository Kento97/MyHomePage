<script setup lang='ts'>
import { onMounted } from 'vue';
import Container from './components/index.vue'
onMounted(() => {
    document.title = "Kento With Vercel"
})
</script>

<template>
    <Container />
</template>

<style scoped>
</style>