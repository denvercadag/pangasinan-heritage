<template>
  <section class="heritage-grid">

    <HeritageCard
      :image="hundredIslandsImage"
      title="Hundred Islands"
      location="Alaminos, Pangasinan"
      description="Explore the famous islands and clear blue waters of one of Pangasinan's most popular destinations."
    />

    <HeritageCard
      :image="bolinaoLighthouseImage"
      title="Bolinao Lighthouse"
      location="Bolinao, Pangasinan"
      description="Discover this historic lighthouse overlooking the beautiful coast of Bolinao."
    />

    <HeritageCard
      :image="balungaoHotSpringImage"
      title="Balungao Hot Spring"
      location="Balungao, Pangasinan"
      description="Relax and enjoy the natural hot spring located at the foot of Mount Balungao."
    />

  </section>
</template>

<script setup>
const baseURL = useRuntimeConfig().app.baseURL

const hundredIslandsImage =
  `${baseURL}images/hundred-islands.jpg`

const bolinaoLighthouseImage =
  `${baseURL}images/bolinao-lighthouse.jpg`

const balungaoHotSpringImage =
  `${baseURL}images/balungao-hot-spring.jpg`
</script>

<style scoped>
.heritage-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}

@media (min-width: 768px) {
  .heritage-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .heritage-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>