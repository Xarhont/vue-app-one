<script setup>
import Button from "./components/Button.vue";
import Stat from "./components/Stat.vue";
import CitySelect from "./components/CitySelect.vue";
import {computed, ref} from "vue";


let savedCity = ref("Moscow");
let data = ref({
  humidity: 90,
});

const dataModified = computed(() => {
  return {
    label: "Влажность",
    stat: data.value.humidity + '%',
  }
})

function getCity(city) {
  savedCity.value = city;
  data.value.humidity = 20
}
</script>

<template>
  <main class="main">
    {{ savedCity }}
    <Stat v-bind="dataModified"/>
    <Stat label="Осадки" stat="0%"/>
    <CitySelect @select-city="getCity"/>
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 50px;
  border-radius: 25px;
}
</style>
