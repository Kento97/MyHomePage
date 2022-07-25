<script setup lang='ts'>
import Plum from './Plum.vue'
import Header from './Header.vue'
import Contact from './Contact.vue'
import Info from './Info.vue'
import { computed } from 'vue';
import isNight from '@/utils/storage';

const textColor = computed(() => (isNight.value ? '#bbb' : '#555'))
const titleColor = computed(() => (isNight.value ? '#fff' : '#000'))
</script>

<template>
    <Header />
    <Info />
    <Contact />
    <Plum />
</template>

<style>
.text-color {
    color: v-bind(textColor);
}

.title-color {
    color: v-bind(titleColor);
}
</style>