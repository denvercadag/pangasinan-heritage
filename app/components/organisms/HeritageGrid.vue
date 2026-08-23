<template>
  <section class="heritage-grid">

    <!-- HUNDRED ISLANDS -->
    <HeritageCard
      :image="hundredIslandsImage"
      title="Hundred Islands"
      location="Alaminos, Pangasinan"
      description="Explore the famous islands and clear blue waters of one of Pangasinan's most popular destinations."
      @learn-more="openSite('hundred-islands')"
    />

    <!-- BOLINAO LIGHTHOUSE -->
    <HeritageCard
      :image="bolinaoLighthouseImage"
      title="Bolinao Lighthouse"
      location="Bolinao, Pangasinan"
      description="Discover this historic lighthouse overlooking the beautiful coast of Bolinao."
      @learn-more="openSite('bolinao-lighthouse')"
    />

    <!-- BALUNGAO HOT SPRING -->
    <HeritageCard
      :image="balungaoHotSpringImage"
      title="Balungao Hot Spring"
      location="Balungao, Pangasinan"
      description="Relax and enjoy the natural hot spring located at the foot of Mount Balungao."
      @learn-more="openSite('balungao-hot-spring')"
    />

    <!-- LEARN MORE POPUP -->
    <div
      v-if="selectedSite"
      class="site-popup"
      role="dialog"
      aria-modal="true"
      :aria-label="selectedSite.title"
      @click.self="closeSite"
    >
      <div class="site-popup-content">

        <button
          type="button"
          class="site-popup-close"
          aria-label="Close information"
          @click="closeSite"
        >
          ×
        </button>

        <img
          :src="selectedSite.image"
          :alt="selectedSite.title"
          class="site-popup-image"
        >

        <p class="site-popup-location">
          {{ selectedSite.location }}
        </p>

        <h2>
          {{ selectedSite.title }}
        </h2>

        <p class="site-popup-description">
          {{ selectedSite.details }}
        </p>

      </div>
    </div>

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

const selectedSite = ref(null)

const sites = {
  'hundred-islands': {
    title: 'Hundred Islands',
    location: 'Alaminos, Pangasinan',
    image: hundredIslandsImage,
    details:
      'Hundred Islands National Park is one of Pangasinan’s most famous natural attractions. It is known for its beautiful islands, beaches, clear waters, and scenic views. Visitors can enjoy island hopping, swimming, sightseeing, and other outdoor activities.'
  },

  'bolinao-lighthouse': {
    title: 'Bolinao Lighthouse',
    location: 'Bolinao, Pangasinan',
    image: bolinaoLighthouseImage,
    details:
      'Bolinao Lighthouse is a historic landmark located in Bolinao, Pangasinan. The lighthouse stands on an elevated area overlooking the coast and provides visitors with beautiful views of the surrounding landscape and sea.'
  },

  'balungao-hot-spring': {
    title: 'Balungao Hot Spring',
    location: 'Balungao, Pangasinan',
    image: balungaoHotSpringImage,
    details:
      'Balungao Hot Spring is a natural attraction located near Mount Balungao. It is known for its warm spring water, peaceful surroundings, and recreational facilities where visitors can relax and enjoy nature.'
  }
}

function openSite(site) {
  selectedSite.value = sites[site]
}

function closeSite() {
  selectedSite.value = null
}
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
/* LEARN MORE POPUP */

.site-popup {
  position: fixed;
  inset: 0;
  z-index: 9999;

  display: flex;
  align-items: center;
  justify-content: center;

  padding: 25px;
  background: rgba(0, 0, 0, 0.88);
}

.site-popup-content {
  position: relative;

  width: 100%;
  max-width: 650px;

  overflow: hidden;

  background: #111318;
  border: 1px solid rgba(216, 163, 42, 0.5);
  border-radius: 10px;

  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.45);
}

.site-popup-image {
  width: 100%;
  height: 300px;

  display: block;
  object-fit: cover;
}

.site-popup-content h2 {
  margin: 8px 28px 16px;

  color: #ffffff;
  font-size: 32px;
}

.site-popup-location {
  margin: 25px 28px 0;

  color: #d8a32a;
  font-size: 13px;
  font-weight: 700;

  letter-spacing: 2px;
  text-transform: uppercase;
}

.site-popup-description {
  margin: 0;
  padding: 0 28px 30px;

  color: #d1d1d1;
  font-size: 16px;
  line-height: 1.7;
}

.site-popup-close {
  position: absolute;
  top: 15px;
  right: 15px;
  z-index: 2;

  width: 45px;
  height: 45px;

  border: none;
  border-radius: 50%;

  background: #0b0d10;
  color: #ffffff;

  font-size: 30px;
  line-height: 1;

  cursor: pointer;
}

.site-popup-close:hover {
  background: #d8a32a;
  color: #0b0d10;
}

@media (max-width: 600px) {
  .site-popup {
    padding: 15px;
  }

  .site-popup-image {
    height: 220px;
  }

  .site-popup-content h2 {
    font-size: 26px;
  }

  .site-popup-location,
  .site-popup-content h2,
  .site-popup-description {
    margin-left: 20px;
    margin-right: 20px;
  }

  .site-popup-description {
    padding-left: 0;
    padding-right: 0;
  }
}
</style>