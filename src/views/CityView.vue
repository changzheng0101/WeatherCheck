<template>
  <suspense>
    <async-city-view></async-city-view>
    <template #fallback><p>Loading...</p></template>
  </suspense>
</template>

<script setup>
import AsyncCityView from "../components/AsyncCityView.vue";
</script>

