<script setup>
const props = defineProps(['icon', 'title', "subtitle", "bottom"]);
</script>

<template>
  <div class="border-2 border-red-950 backdrop-blur bg-yellow-950/10 flex flex-col justify-center items-center px-5 py-7 rounded-md shadow-lg min-h-[28rem] min-w-[25rem]">
    <i :class="props.icon" class="text-4xl "></i>
    <p class="text-yellow-400 text-xl font-bold my-3 ">{{props.title}}</p>
    <p class="text-orange-300"> {{props.subtitle}}</p>

    <div class="my-4">
      <slot></slot>
    </div>

    <p class="text-sm text-white">{{bottom}}</p>
  </div>
</template>

<style scoped>

</style>