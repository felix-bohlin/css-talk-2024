<script setup lang="ts">
  defineProps<{
    text?: string;
  }>();
</script>

<template>
  <div class="flex flex-nowrap justify-center align-center gap-2 w-full">
    <p>{{ text ?? 'This sparks joy!' }}</p>
    <img
      class="object-contain w-10 drop-shadow-[0_0px_40px_rgba(255,255,2)]"
      src="/kondo.png"
    />
  </div>
</template>
