<script setup>
import Button from "./components/Button.vue";
import ButtonDz from "./components/ButtonDz.vue";
</script>

<template>
  <main class="main">
    <Button>Сохранить</Button>
    <ButtonDz>Начать игру</ButtonDz>
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 50px;
  border-radius: 25px;
}
</style>
