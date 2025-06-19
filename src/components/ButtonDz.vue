<script setup></script>

<template>
  <button class="button-dz">
    <slot></slot>
  </button>
</template>

<style scoped>
.button-dz {
  padding: 16px 10px;
  background: #008bfe;
  border: none;
  border-radius: 100px;
  color: #fff;
  font-weight: 400;
  font-size: 24px;
  width: 335px;
  height: 68px;
  line-height: 36px;
  font-family: "Roboto", sans-serif;
}
</style>
