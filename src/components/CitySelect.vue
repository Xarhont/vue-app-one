<script setup>

import Button from "./Button.vue";
import IconLocation from "../icons/IconLocation.vue";
import {ref} from "vue";

const emit = defineEmits({
  selectCity(payload) {
    return payload;
  }
})

let isEdited = ref(false);

function select() {
  isEdited.value = false;
  emit('selectCity', "London")
}

function edit() {
  isEdited.value = true;
}

</script>

<template>
  {{ isEdited}}
  <Button @click="edit()">
    <IconLocation/>
    Изменить город
  </Button>
  <input/>
  <Button @click="select()">Сохранить</Button>
</template>

<style scoped>

</style>