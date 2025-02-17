<template>
  <div class="landing-page">
    <nav class="navigation">
      <div class="logo">
        <h1 class="brand">antic</h1>
      </div>
      <div class="nav-links" :class="{ active: isMenuOpen }">
        <a href="#" class="nav-link">Products</a>
        <a href="#" class="nav-link">Rooms</a>
        <a href="#" class="nav-link">Services</a>
        <a href="#" class="nav-link">Inspirations</a>
      </div>
      <button
        class="menu-toggle"
        @click="toggleMenu"
        :class="{ active: isMenuOpen }"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
    </nav>

    <main class="content">
      <div class="left-section">
        <div class="category">HOME DESIGN</div>
        <h2 class="title">Elegance for<br />Interiors &<br />Exteriors</h2>
        <p class="description">
          We provide everyone with modern,<br />trendy, quality furniture
        </p>
        <div class="scroll-button">
          <img src="@/assets/scroll.svg" alt="Scroll down" />
        </div>
      </div>
      <div class="right-section">
        <div class="comments-icon">
          <img src="@/assets/comments.svg" alt="Comments" />
        </div>
        <img
          src="@/assets/home.svg"
          alt="Elegant pendant lamps"
          class="hero-image"
        />
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "LandingPage",
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
};
</script>

<style scoped>
.landing-page {
  min-height: 100vh;
  background-color: #f3eee8;
  position: relative;
  overflow: hidden;
}

.navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2rem 4.5rem;
  position: relative;
  z-index: 100;
}

.brand {
  font-family: "Merriweather", serif;
  color: #a06056;
  font-size: 34px;
  font-weight: 700;
  margin-left: 150px;
  margin-right: 32px;
}

.nav-links {
  display: flex;
  gap: 24px;
  margin-right: auto;
}

.nav-link {
  font-family: "Varta", sans-serif;
  color: #706458;
  text-decoration: none;
  font-size: 1rem;
  font-weight: 400;
}
.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  width: 24px;
  height: 18px;
  position: relative;
  padding: 0;
}

.menu-toggle span {
  display: block;
  position: absolute;
  height: 2px;
  width: 100%;
  background: #706458;
  transition: 0.2s ease-in-out;
}

.menu-toggle span:nth-child(1) {
  top: 0;
}
.menu-toggle span:nth-child(2) {
  top: 8px;
}
.menu-toggle span:nth-child(3) {
  top: 16px;
}

.menu-toggle.active span:nth-child(1) {
  transform: rotate(45deg);
  top: 8px;
}

.menu-toggle.active span:nth-child(2) {
  opacity: 0;
}

.menu-toggle.active span:nth-child(3) {
  transform: rotate(-45deg);
  top: 8px;
}

.content {
  display: flex;
  position: relative;
  height: calc(100vh - 100px);
}

.left-section {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: 10%;
  position: relative;
  z-index: 2;
}

.category {
  font-family: "Varta", sans-serif;
  color: #a06056;
  font-size: 14px;
  margin-bottom: 1.5rem;
  letter-spacing: 0.1em;
}

.title {
  font-family: "Merriweather", serif;
  color: #a06056;
  font-size: 3.75rem;
  line-height: 1.2;
  margin-bottom: 2rem;
  font-weight: 400;
}

.description {
  font-family: "Varta", sans-serif;
  color: #706458e5;
  font-size: 1.125rem;
  line-height: 1.6;
  margin-bottom: 4rem;
}

.scroll-button img {
  width: 48px;
  height: 48px;
  cursor: pointer;
}

.right-section {
  position: absolute;
  top: -100px;
  right: -100px;
  width: 60%;
  height: 120%;
  overflow: hidden;
}

.hero-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.comments-icon {
  position: absolute;
  margin-right: 22px;
  right: 120px;
  top: 35px;
  z-index: 10;
}

.comments-icon img {
  width: 48px;
  height: 48px;
  cursor: pointer;
}

@media (max-width: 1440px) {
  .navigation {
    padding: 2rem 3rem;
  }

  .brand {
    font-size: clamp(28px, 2.5vw, 34px);
    margin-left: 0px;
  }
  .comments-icon{
    margin-right: 22px;

  }

  .nav-links {
    gap: clamp(16px, 0.5vw, 24px);
  }

  .nav-link {
    font-size: clamp(14px, 1vw, 16px);
  }

  .left-section {
    padding-left: 5%;
  }

  .title {
    font-size: clamp(2.8rem, 5vw, 3.75rem);
  }

  .description {
    font-size: clamp(1rem, 1.2vw, 1.125rem);
  }

  .right-section {
    width: 55%;
  }
}

@media (max-width: 1024px) {
  .landing-page {
    background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4));
  }

  .navigation {
    padding: 1.5rem;
  }

  .brand {
    color: #ffffff;
    font-size: 1.5rem;
  }

  .menu-toggle {
    display: block;
  }

  .nav-links {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: #f3eee8;
    margin: 0;
    padding: 6rem 1.5rem;
    flex-direction: column;
    gap: 2rem;
    transform: translateX(-100%);
    transition: transform 0.3s ease;
  }

  .nav-links.active {
    transform: translateX(0);
  }

  .content {
    flex-direction: column;
    height: auto;
    min-height: calc(100vh - 80px);
  }

  .left-section {
    padding: 2rem 1.5rem;
    text-align: center;
    align-items: center;
  }

  .category {
    color: #ffffff;
    font-size: 0.875rem;
    margin-bottom: 1rem;
  }

  .title {
    color: #ffffff;
    font-size: 2.5rem;
    margin-bottom: 1.5rem;
  }

  .description {
    color: #ffffff;
    font-size: 1rem;
    margin-bottom: 2rem;
  }

  .right-section {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
  }

  .hero-image {
    object-fit: cover;
    width: 100%;
    height: 100vh;
  }

  .comments-icon {
    display: none;
  }
}
</style>
