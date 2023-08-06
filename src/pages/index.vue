<script setup lang="ts" generic="T extends any, O extends any">
defineOptions({
  name: 'IndexPage',
})
</script>

<template>
  <div>
    <div i-carbon-campsite inline-block text-4xl />
    <div mb-lg text-center>
      <div>
        مضاف حديثا
      </div>
    </div>
    <PrototypeHome />
  </div>
</template>
