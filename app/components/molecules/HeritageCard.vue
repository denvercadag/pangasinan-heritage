<template>
  <article class="heritage-card">
    <div class="image-wrapper">
      <BaseImage :src="image" :alt="title" />
    </div>

    <div class="heritage-card__content">
      <p class="location">{{ location }}</p>

      <h2>{{ title }}</h2>

      <BaseText>
        {{ description }}
      </BaseText>

      <BaseButton @click="$emit('learn-more')">
       Learn More
    </BaseButton>
    </div>
  </article>
</template>

<script setup>
defineEmits(['learn-more'])

defineProps({
  image: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  location: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.heritage-card {
  overflow: hidden;
  background: #111318;
  border: 1px solid rgba(216, 163, 42, 0.25);
  border-radius: 8px;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);

  display: flex;
  flex-direction: column;
  height: 100%;

  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}

.heritage-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 18px 35px rgba(0, 0, 0, 0.25);
}

.image-wrapper {
  height: 230px;
  overflow: hidden;
}

.image-wrapper :deep(img) {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 0;
}

.heritage-card__content {
  display: flex;
  flex-direction: column;
  gap: 14px;
  padding: 24px;

  flex: 1;
}

.heritage-card__content :deep(.base-button) {
  margin-top: auto;
  width: 100%;
}

.location {
  margin: 0;
  color: #d8a32a;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
}

.heritage-card h2 {
  margin: 0;
  color: #ffffff;
  font-size: 26px;
}

.heritage-card__content :deep(.base-text) {
  color: #c8c8c8;
}

@media (max-width: 600px) {
  .image-wrapper {
    height: 210px;
  }

  .heritage-card__content {
    padding: 20px;
  }
}
</style>