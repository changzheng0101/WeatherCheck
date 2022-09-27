

<template>
  <main class="container text-white">
    <div class="pt-4 mb-8 relative">
      <input
        v-model="searchQuery"
        @input="getSearchResults"
        autocomplete="noAuto"
        type="text"
        placeholder="Search for a city or state"
        class="
          py-2
          px-1
          w-full
          bg-transparent
          border-b
          focus:outline-none
          focus:border-weather-secondary
          focus:shadow-[0px_1px_0_0_#004E71]
        "
      />
      <ul
        v-if="mapboxQueryResult"
        class="
          absolute
          bg-weather-secondary
          text-white
          w-full
          shadow-md
          py-2
          px-1
          top-[66px]
        "
      >
        <li
          v-for="searchResult in mapboxQueryResult"
          :key="searchResult.id"
          class="py-2 cursor-pointer"
        >
          {{ searchResult.place_name }}
        </li>
      </ul>
    </div>
  </main>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";

const mapboxAPIKey =
  "pk.eyJ1Ijoiam9obmtvbWFybmlja2kiLCJhIjoiY2t5NjFzODZvMHJkaDJ1bWx6OGVieGxreSJ9.IpojdT3U3NENknF6_WhR2Q";
const searchQuery = ref("");
const queryTimeout = ref(null);
const mapboxQueryResult = ref(null);

const getSearchResults = () => {
  clearTimeout(queryTimeout.value);
  if (searchQuery.value !== "") {
    queryTimeout.value = setTimeout(async () => {
      const result = await axios.get(
        `https://api.mapbox.com/geocoding/v5/mapbox.places/${searchQuery.value}.json?access_token=${mapboxAPIKey}&types=place`
      );
      mapboxQueryResult.value = result.data.features;
    }, 300);
  } else {
    mapboxQueryResult.value = null;
  }
};
</script>