<template>
  <header class="site-header">
    <div class="header-container">

      <a href="#" class="logo">
        <span class="logo-main">PANGASINAN</span>
        <span class="logo-sub">HERITAGE</span>
      </a>

      <nav class="navigation" aria-label="Main navigation">
        <NavigationItem label="Home" href="#" />
        <NavigationItem label="Heritage Sites" href="#heritage" />
        <NavigationItem label="About" href="#about" />
        <NavigationItem label="Gallery" href="#gallery" />
        <NavigationItem label="Contact" href="#contact" />
      </nav>

      <a href="#heritage" class="explore-button">
        Explore Map
      </a>

    </div>
  </header>
</template>

<style scoped>
.site-header {
  position: relative;
  z-index: 100;
  background: #0b0d10;
  border-bottom: 1px solid rgba(216, 163, 42, 0.25);
}

.header-container {
  max-width: 1300px;
  margin: 0 auto;
  padding: 18px 30px;

  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 30px;
}

/* LOGO */

.logo {
  display: flex;
  flex-direction: column;
  text-decoration: none;
}

.logo-main {
  color: #ffffff;
  font-size: 20px;
  font-weight: 800;
  letter-spacing: 2px;
}

.logo-sub {
  margin-top: 3px;
  color: #d8a32a;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 5px;
}

/* NAVIGATION */

.navigation {
  display: flex;
  align-items: center;
  gap: 28px;
}

/* EXPLORE BUTTON */

.explore-button {
  padding: 12px 20px;

  background: #d8a32a;
  color: #0b0d10;

  border-radius: 4px;

  font-size: 13px;
  font-weight: 800;
  letter-spacing: 1px;
  text-decoration: none;
  text-transform: uppercase;

  transition: 0.2s ease;
}

.explore-button:hover {
  background: #f0bd43;
}

/* MOBILE */

@media (max-width: 900px) {
  .header-container {
    flex-wrap: wrap;
    justify-content: center;
  }

  .logo {
    width: 100%;
    align-items: center;
  }

  .navigation {
    gap: 18px;
    flex-wrap: wrap;
    justify-content: center;
  }
}

@media (max-width: 600px) {
  .header-container {
    padding: 16px 20px;
  }

  .navigation {
    gap: 14px;
  }

  .explore-button {
    width: 100%;
    text-align: center;
  }
}
</style>