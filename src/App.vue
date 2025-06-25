<script setup>
import { computed, ref } from "vue";
import PanelRight from "./components/PanelRight.vue";

const API_ENDPOINT = "http://api.weatherapi.com/v1";

let data = ref();
let error = ref();
let activeIndex = ref(0);

async function getCity(city) {
  const params = new URLSearchParams({
    q: city,
    lang: "ru",
    key: "f81cfd4981714ea395e54302252506",
    days: 3,
  });
  const res = await fetch(`${API_ENDPOINT}/forecast.json?${params.toString()}`);
  if (res.status != 200) {
    error.value = await res.json();
    data.value = null;
    return;
  }
  error.value = null;
  data.value = await res.json();
}
</script>

<template>
  <main class="main">
    <div class="left"></div>
    <div class="right">
      <PanelRight
        :data
        :error
        :active-index="activeIndex"
        @select-index="(index) => (activeIndex = index)"
        @select-city="(city) => getCity(city)"
      />
    </div>
  </main>
</template>

<style scoped>
.main {
  display: flex;
  align-items: center;
  justify-content: center;
}
.right {
  background: var(--color-bg-main);
  padding: 50px;
  border-radius: 0 25px 25px 0;
}

.left {
  width: 500px;
  height: 680px;
  border-radius: 30px;
  background-image: url("public/bg.png");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
