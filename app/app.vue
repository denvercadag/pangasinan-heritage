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

          <BaseButton>
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
    <img
      src="/images/hundred-islands.jpg"
      alt="Hundred Islands in Alaminos, Pangasinan"
    >

    <img
      src="/images/bolinao-lighthouse.jpg"
      alt="Bolinao Lighthouse in Pangasinan"
    >

    <img
      src="/images/balungao-hot-spring.jpg"
      alt="Balungao Hot Spring in Pangasinan"
    >
  </div>
</section>
<!-- CONTACT -->
<section id="contact" class="contact-section">
  <div class="contact-content">
    <p class="contact-label">GET IN TOUCH</p>

    <h2>Discover More of Pangasinan</h2>

    <p>
      Learn more about Pangasinan's heritage sites, culture,
      and natural attractions.
    </p>

    <a href="#heritage" class="contact-button">
      Explore Heritage Sites
    </a>
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