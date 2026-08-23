<template>
  <div>
    <HeaderNavigation />

    <main>
      <!-- HERO -->
      <section class="hero">
        <div class="hero-content">
          <p class="hero-label">EXPLORE PANGASINAN</p>

          <h1>
            Discover the Heritage of
            <span>Pangasinan</span>
          </h1>

          <p class="hero-description">
            Historic landmarks. Natural wonders.
            Timeless stories.
          </p>

          <BaseButton @click="scrollToHeritage">
        Explore Heritage Sites
      </BaseButton> 
        </div>
      </section>

      <!-- HERITAGE SITES -->
      <section id="heritage" class="heritage-section">
        <div class="section-heading">
          <p>DISCOVER OUR PROVINCE</p>
          <h2>Our Heritage Sites</h2>
        </div>

        <HeritageGrid />
      </section>

      <!-- ABOUT -->
      <section id="about" class="about-section">
        <div class="about-content">
          <p class="about-label">ABOUT PANGASINAN</p>

          <h2>
            Culture, Nature,
            <span>and Heritage</span>
          </h2>

          <p class="about-description">
            Pangasinan is home to beautiful natural attractions,
            historic landmarks, and cultural destinations that reflect
            the province's rich identity and history.
          </p>

          <p class="about-description">
            The Pangasinan Heritage Digital Showcase helps visitors
            discover and appreciate these remarkable destinations.
          </p>
        </div>

        <div class="about-highlight">
          <span class="highlight-number">3</span>
          <span class="highlight-text">Featured Heritage Sites</span>
        </div>
      </section>

      <!-- GALLERY -->
      <section id="gallery" class="gallery-section">
        <div class="section-heading">
          <p>EXPLORE PANGASINAN</p>
          <h2>Heritage Gallery</h2>
        </div>

        <div class="gallery-grid">

          <!-- HUNDRED ISLANDS -->
          <button
            type="button"
            class="gallery-item"
            aria-label="Enlarge Hundred Islands image"
            @click="openImage(hundredIslandsImage, 'Hundred Islands')"
          >
            <img
              :src="hundredIslandsImage"
              alt="Hundred Islands in Alaminos, Pangasinan"
            >
          </button>

          <!-- BOLINAO LIGHTHOUSE -->
          <button
            type="button"
            class="gallery-item"
            aria-label="Enlarge Bolinao Lighthouse image"
            @click="openImage(bolinaoLighthouseImage, 'Bolinao Lighthouse')"
          >
            <img
              :src="bolinaoLighthouseImage"
              alt="Bolinao Lighthouse in Pangasinan"
            >
          </button>

          <!-- BALUNGAO HOT SPRING -->
          <button
            type="button"
            class="gallery-item"
            aria-label="Enlarge Balungao Hot Spring image"
            @click="openImage(balungaoHotSpringImage, 'Balungao Hot Spring')"
          >
            <img
              :src="balungaoHotSpringImage"
              alt="Balungao Hot Spring in Pangasinan"
            >
          </button>

        </div>

        <!-- IMAGE POPUP -->
        <div
          v-if="selectedImage"
          class="lightbox"
          role="dialog"
          aria-modal="true"
          :aria-label="selectedTitle"
          @click.self="closeImage"
        >
          <button
            type="button"
            class="lightbox-close"
            aria-label="Close enlarged image"
            @click="closeImage"
          >
            ×
          </button>

          <img
            :src="selectedImage"
            :alt="selectedTitle"
            class="lightbox-image"
          >

          <p class="lightbox-title">
            {{ selectedTitle }}
          </p>
        </div>
      </section>

      <!-- FOOTER -->
      <footer class="site-footer">
        <div class="footer-content">
          <div>
            <h3>Pangasinan Heritage</h3>
            <p>
              Celebrating the culture, history, and natural beauty of Pangasinan.
            </p>
          </div>

          <p class="copyright">
            © 2026 Pangasinan Heritage Digital Showcase (KLBMN)
          </p>
        </div>
      </footer>
    </main>
  </div>
</template>

<script setup>
const baseURL = useRuntimeConfig().app.baseURL

const hundredIslandsImage =
  `${baseURL}images/hundred-islands.jpg`

const bolinaoLighthouseImage =
  `${baseURL}images/bolinao-lighthouse.jpg`

const balungaoHotSpringImage =
  `${baseURL}images/balungao-hot-spring.jpg`

const selectedImage = ref('')
const selectedTitle = ref('')

function openImage(image, title) {
  selectedImage.value = image
  selectedTitle.value = title
}

function closeImage() {
  selectedImage.value = ''
  selectedTitle.value = ''
}

function handleKeydown(event) {
  if (event.key === 'Escape' && selectedImage.value) {
    closeImage()
  }
}

onMounted(() => {
  window.addEventListener('keydown', handleKeydown)
})

onUnmounted(() => {
  window.removeEventListener('keydown', handleKeydown)
})

function scrollToHeritage() {
  document.getElementById('heritage')?.scrollIntoView({
    behavior: 'smooth'
  })
}

useHead({
  title: 'Pangasinan Heritage Digital Showcase',

  meta: [
    {
      name: 'description',
      content:
        'Explore the heritage sites, culture, history, and natural attractions of Pangasinan including Hundred Islands, Bolinao Lighthouse, and Balungao Hot Spring.'
    },
    {
      name: 'viewport',
      content: 'width=device-width, initial-scale=1'
    }
  ],

  htmlAttrs: {
    lang: 'en'
  }
})
</script>