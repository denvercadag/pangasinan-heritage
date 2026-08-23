<template>
  <form class="search-form" @submit.prevent>
    <label for="heritage-search" class="sr-only">
      Search heritage sites
    </label>

    <input
      id="heritage-search"
      type="search"
      placeholder="Search heritage sites..."
      class="search-input"
    >

    <BaseButton type="submit">
      Search
    </BaseButton>
  </form>
</template>

<style scoped>
.search-form {
  display: flex;
  gap: 10px;
  width: 100%;
}

.search-input {
  flex: 1;
  padding: 12px 14px;
  border: 1px solid #d1d5db;
  border-radius: 8px;
  font-size: 16px;
}

.search-input:focus {
  outline: 2px solid #0f766e;
  outline-offset: 2px;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

@media (max-width: 480px) {
  .search-form {
    flex-direction: column;
  }
}
</style>