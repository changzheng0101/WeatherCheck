<template>
  <div class="flex py-6 px-3 rounded-md shadow-md cursor-pointer mb-2">
    <div class="flex flex-col flex-1">
      <animated-placeholder class="w-[50%]" />
      <animated-placeholder class="w-[50%]" />
    </div>
    <div class="flex flex-col gap-2 items-end flex-1">
      <animated-placeholder class="max-w-[50px] w-full" />
      <animated-placeholder class="max-w-[65px] w-full" />
    </div>
  </div>
</template>

<script setup>
import AnimatedPlaceholder from './AnimatedPlaceholder.vue';
</script>
