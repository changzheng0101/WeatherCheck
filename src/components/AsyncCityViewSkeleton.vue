<template>
  <div class="flex flex-col items-center">
    <!-- Weather Overview -->
    <div class="flex flex-col py-12 items-center w-[200px]">
      <animated-placeholder class="max-w-[300px] w-full mb-12 h-[60px]" />
      <animated-placeholder class="max-w-[300px] w-full mb-12" />
      <animated-placeholder class="max-w-[300px] h-[100px] w-full mb-8" />
      <animated-placeholder class="max-w-[300px] w-full mb-8" />
      <animated-placeholder class="max-w-[300px] h-[75px] w-full" />
    </div>

    <!-- Hourly Weather -->
    <div class="max-w-screen-md w-full py-12">
      <animated-placeholder class="max-w-screen-md h-[130px] w-full mb-12" />
    </div>

    <!-- Weekly Weather -->
    <div class="max-w-screen-md w-full py-12">
      <animated-placeholder class="max-w-screen-md h-[200px] w-full mb-12" />
    </div>
  </div>
</template>

<script setup>
import AnimatedPlaceholder from "./AnimatedPlaceholder.vue";
</script>
