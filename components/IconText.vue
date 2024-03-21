<script setup lang="ts">
defineProps<{
  align?: 'left' | 'right';
  text: string
}>()
</script>

<template>
  <p :class="align === 'right' && 'text-right mr-7'" class="!my-2">
    <span :class="align === 'right' && 'justify-end'" class="flex items-center gap-1">
      <span v-if="align !== 'right'" class="opacity-50 text-sm">
        <slot />
      </span>

      {{ text }}

      <span v-if="align === 'right'" class="opacity-50 text-sm">
        <slot />
      </span>
    </span>
  </p>
</template>
