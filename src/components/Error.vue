<script setup>
import { defineComponent } from "vue";

const props = defineProps({
  error: String,
});
</script>

<template>
  <div v-if="props.error" class="error">{{ props.error }}</div>
</template>

<style scoped>
.error {
  font-size: 18px;
  padding: 15px;
  text-align: center;
  background: var(--color-bg-card);
  border-radius: 0 0 25px 25px;
  margin-top: -50px;
  margin-bottom: 60px;
}
</style>
