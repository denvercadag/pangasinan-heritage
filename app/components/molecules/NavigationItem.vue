<template>
  <a :href="href" class="nav-item">
    {{ label }}
  </a>
</template>

<script setup>
defineProps({
  label: {
    type: String,
    required: true
  },
  href: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.nav-item {
  position: relative;
  color: #ffffff;
  text-decoration: none;
  font-size: 14px;
  font-weight: 600;
  transition: color 0.2s ease;
}

.nav-item:hover {
  color: #d8a32a;
}

.nav-item::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -7px;

  width: 0;
  height: 2px;

  background: #d8a32a;
  transition: width 0.2s ease;
}

.nav-item:hover::after {
  width: 100%;
}

.nav-item:focus {
  outline: 2px solid #d8a32a;
  outline-offset: 5px;
}
</style>