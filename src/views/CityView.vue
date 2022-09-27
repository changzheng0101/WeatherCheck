<template>
  <suspense>
    <async-city-view></async-city-view>
    <template #fallback>
      <async-city-view-skeleton />
    </template>
  </suspense>
</template>

<script setup>
import AsyncCityView from "../components/AsyncCityView.vue";
import AsyncCityViewSkeleton from "../components/AsyncCityViewSkeleton.vue";
</script>

