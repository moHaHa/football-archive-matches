<script setup lang="ts" generic="T extends any, O extends any">
const { url } = defineProps(['url'])
</script>

<template>
  <div>
    <iframe allow="autoplay; fullscreen; picture-in-picture" frameborder="0" :src="url" allowfullscreen h-300px w-full rounded />
  </div>
</template>
