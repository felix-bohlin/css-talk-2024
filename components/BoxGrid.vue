<script setup>
import { computed, ref, watchEffect } from 'vue';
import {codeToHtml} from 'shiki'

const minValue = ref('30')
const gridTemplateColumns = computed(() => `repeat(auto-fill, minmax(${minValue.value}ch, 1fr))`)

const code = computed(() => `<Box sx={{
  display: grid;
  gap: 1rem;
  grid-template-columns: ${gridTemplateColumns.value};
}}>
 {fields.map((item) => item)}
</Box>
`)

let html = await codeToHtml(code.value, {
    lang: 'tsx',
    theme: 'dark-plus'
  })

watchEffect(async () => {
  html = await codeToHtml(code.value, {
    lang: 'tsx',
    theme: 'dark-plus'
  })

})
</script>

<template>
  <code v-html="html" class="p-2 bg-gray-100" />

  <div class="flex justify-end my-2.5 flex gap-2">

    <input type="range" v-model="minValue" min="15" max="45" class="accent-indigo-500" />
  </div>


  <div class="wrapper">
    <input type="text" placeholder="First name" class="p-2 w-full bg-gray-100" />
    <input type="text" placeholder="Last name" class="p-2 w-full bg-gray-100" />
    <input type="text" placeholder="Email" class="p-2 w-full" />
    <select class="p-2 w-full">
      <option value="" disabled selected>Choose stuff</option>
      <option>English</option>
      <option>Option 2</option>
      <option>Option 3</option>
    </select>
  </div>
</template>

<style scoped>
  .wrapper {
    @apply gap-4 rounded p-2 border-2 border-zinc-500/50;
    display: grid;
    grid-template-columns: v-bind(gridTemplateColumns);
    overflow: auto;
    resize: both;
    max-width: 100%;


    > * {
      @apply grid place-items-center rounded;
      max-height: 40px;
      background: transparent;
      border: 1px solid gray;
    }
  }
</style>
