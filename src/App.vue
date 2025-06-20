<script setup>
import Button from "./components/Button.vue";
import Stat from "./components/Stat.vue";
import CitySelect from "./components/CitySelect.vue";

const data = {
  label: "Влажность",
  stat: "90%"
}

function getCity(city) {
  console.log(city);
}
</script>

<template>
  <main class="main">
    <Stat v-bind="data"/>
    <Stat label="Осадки" stat="0%"/>
    <CitySelect @select-city="getCity" />
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 50px;
  border-radius: 25px;
}
</style>
