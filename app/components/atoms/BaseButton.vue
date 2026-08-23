<template>
  <button class="base-button">
    <slot />
  </button>
</template>

<style scoped>
.base-button {
  padding: 14px 24px;
  border: 2px solid #d8a32a;
  border-radius: 4px;

  background: #d8a32a;
  color: #0b0d10;

  font-size: 14px;
  font-weight: 800;
  letter-spacing: 1px;
  text-transform: uppercase;

  cursor: pointer;

  transition: 0.2s ease;
}

.base-button:hover {
  background: transparent;
  color: #d8a32a;
}

.base-button:focus {
  outline: 3px solid #ffffff;
  outline-offset: 3px;
}
</style>