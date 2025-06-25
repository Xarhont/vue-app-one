<script setup lang="ts">
import IconSun from "../icons/weather/IconSun.vue";
import IconRain from "../icons/weather/IconRain.vue";
import IconCloud from "../icons/weather/IconCloud.vue";

const { weatherCode, temp, date } = defineProps({
  weatherCode: String,
  temp: String,
  date: Date,
});
</script>

<template>
  <button class="day-card">
    <IconSun v-if="weatherCode === 1000" />
    <IconRain v-if="weatherCode === 1063" />
    <IconCloud v-if="weatherCode === 1003" />
    <div class="day-card__day">
      {{ date.toLocaleDateString("ru-RU", { weekday: "short" }) }}
    </div>
    <div class="day-card__temp">{{ temp }} °C</div>
  </button>
</template>

<style scoped>
.day-card {
  color: var(--color-primary);
  padding: 20px 24px;
  background-color: var(--color-bg-card);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 15px;
  border-radius: 10px;
  box-shadow: 1px 2px 4px 0px #222831;
  border: none;
  cursor: pointer;
  width: 100%;
}
.day-card:hover {
  background-color: #3a434f;
}
.day-card__day {
  font-size: 20px;
  font-weight: 400;
}

.day-card__temp {
  font-size: 20px;
  font-weight: 700;
}
</style>
