<template>
  <img
    class="base-image"
    :src="src"
    :alt="alt"
    loading="lazy"
  >
</template>

<script setup>
defineProps({
  src: {
    type: String,
    required: true
  },
  alt: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.base-image {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 12px;
  object-fit: cover;
}
</style>