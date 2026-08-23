<template>
  <section class="heritage-grid">
    <HeritageCard
      image="/images/hundred-islands.jpg"
      title="Hundred Islands"
      location="Alaminos, Pangasinan"
      description="Explore the famous islands and clear blue waters of one of Pangasinan's most popular destinations."
    />

    <HeritageCard
      image="/images/bolinao-lighthouse.jpg"
      title="Bolinao Lighthouse"
      location="Bolinao, Pangasinan"
      description="Discover this historic lighthouse overlooking the beautiful coast of Bolinao."
    />

    <HeritageCard
      image="/images/balungao-hot-spring.jpg"
      title="Balungao Hot Spring"
      location="Balungao, Pangasinan"
      description="Relax and enjoy the natural hot spring located at the foot of Mount Balungao."
    />
  </section>
</template>

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