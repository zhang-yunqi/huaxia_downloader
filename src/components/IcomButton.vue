<script setup>
const props = defineProps(['icon','text']);
</script>

<template>
  <div class="flex rounded bg-red-900 p-3 shadow-md space-x-2 hover:border active:bg-orange-300">
    <i :class="props.icon"></i>
    <span>{{props.text}}</span>

  </div>
</template>

<style scoped>

</style>