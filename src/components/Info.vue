<script setup lang="ts">
const info = [
  'I have no special talent. I am only passionately curious.',
  'Wisely, and slow. They stumble that run fast.',
  'If you judge people, you have no time to love them.',
  'All that we are is the result of what we have thought.'
]
</script>

<template>
  <div class="flex justify-center pl-5 pr-5 my ">
    <ul class="text-color w-150">
      <li class="list-none lh-10 text-[1.3em] font-[KaiWen] px" v-for="(item, index) of info" :key="index">{{ item }}
      </li>
    </ul>
  </div>
</template>
