<script setup></script>

<template>
  <button class="button">
    <div>
      <slot name="icon"></slot>
    </div>
    <slot></slot>
  </button>
</template>

<style scoped>
.button {
  border: none;
  border-radius: 10px;
  background: var(--gradient);
  padding: 14px;
  height: 53px;
  width: 100%;
  font-family: var(--font);
  font-size: 20px;
  font-weight: 600;
  color: var(--color-primary);
  cursor: pointer;
  display: flex;
  gap: 9px;
  align-items: center;
  justify-content: center;
}

.button:hover {
  background: var(--gradient-inverted);
}
</style>
