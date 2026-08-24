<template>
  <a
    :href="fullHref"
    class="nav-item"
  >
    {{ label }}
  </a>
</template>

<script setup>
const props = defineProps({
  label: {
    type: String,
    required: true
  },

  href: {
    type: String,
    required: true
  }
})

const baseURL = useRuntimeConfig().app.baseURL

const fullHref = computed(() => {
  if (props.href === '#') {
    return baseURL
  }

  if (props.href.startsWith('#')) {
    return `${baseURL}${props.href}`
  }

  return props.href
})
</script>

<style scoped>
.nav-item {
  color: #ffffff;
  text-decoration: none;
  font-size: 16px;
  font-weight: 600;
}

.nav-item:hover {
  color: #d8a32a;
}

.nav-item:focus {
  outline: 2px solid #d8a32a;
  outline-offset: 4px;
}
</style>