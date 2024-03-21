<script setup lang="ts">
defineProps<{
  align?: 'left' | 'right';
  text: string
}>()
</script>

<template>
  <h5 :class="align === 'right' ? 'text-right mr-7' : '-ml-4.5 mt-1'" class="mt-1">
    <span :class="align === 'right' && 'justify-end'" class="flex items-center gap-1">
      <span v-if="align !== 'right'" class="opacity-50 text-sm">
        <slot />
      </span>

      {{ text }}

      <span v-if="align === 'right'" class="opacity-50 text-sm">
        <slot />
      </span>
    </span>
  </h5>
</template>
