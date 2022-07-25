<script setup lang="ts">
import { Icon } from '@iconify/vue'
import isNight from '../utils/storage'
import { computed, ref } from 'vue';

let theme = computed(() =>
  isNight.value ? 'color-gray hover-color-white' : 'color-gray-500 hover-color-black'
)

let style = computed(() => {
  return {
    color: isNight.value ? 'white' : 'black'
  }
})

const contacts = [
  { icon: 'akar-icons:github-fill', text: 'Kento', link: 'https://github.com/Kento97' },
  { icon: 'ri:qq-line', text: '1257148430', link: '' },
  { icon: 'ri:wechat-2-line', text: '18761074748', link: '' },
  // { icon: 'uit:blogger-alt', text: 'Blog', link: 'https://blog.mphy.top' },
  // { icon: 'bx:book-bookmark', text: 'Notebook', link: 'http://docs.mphy.top' },
  // { icon: 'iconoir:profile-circled', text: 'Resume', link: 'http://resume.mphy.top' }
]

let currentIndex = ref(-1)
const toggle = (index: number) => {
  if (currentIndex.value === index) {
    currentIndex.value = -1
  } else {
    currentIndex.value = index
  }
}
</script>

<template>
  <hr class="w-10 ml-[50%] relative right-5 mb-4 bg-gray-100 " />
  <ul class="flex justify-center list-none">
    <li v-for="({ icon, text, link }, index) of contacts" :key="icon"
      class="flex flex-column flex-wrap w-13 justify-center h-20">
      <div class="w-8 h-8">
        <Icon :icon="icon" class="w-[100%] h-[100%] cursor-pointer" :class="theme" @click="toggle(index)"
          :style="currentIndex === index ? style : ''" />
      </div>

      <template v-if="currentIndex === index">
        <a v-if="link !== ''" :href="link" target="_blank" class="text-color text-[.9em]">
          {{ text }}
        </a>
        <span class="text-[.9em] text-color" v-else>
          {{ text }}
        </span>
      </template>
    </li>
  </ul>
  <footer class="flex justify-center text-[1em] m-5">
    <p class="text-color w-150 font-[KaiWen] text-center">
      ©Kento 2022
    </p>
  </footer>
</template>
