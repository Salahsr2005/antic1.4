<template>
  <footer class="footer">
    <div class="content">
      <!-- Logo and Navigation -->
      <nav class="navigation">
        <div class="logotype">antic</div>

        <div class="nav-sections">
          <!-- About -->
          <div class="nav-section">
            <h3 class="nav-title">About</h3>
            <div class="nav-links">
              <a href="#" class="nav-link">Our story</a>
              <a href="#" class="nav-link">Our stores</a>
              <a href="#" class="nav-link">Our partners</a>
            </div>
          </div>

          <!-- Services -->
          <div class="nav-section">
            <h3 class="nav-title">Services</h3>
            <div class="nav-links">
              <a href="#" class="nav-link">Click and collect</a>
              <a href="#" class="nav-link">Conception</a>
              <a href="#" class="nav-link">Installation</a>
              <a href="#" class="nav-link">Advices</a>
              <a href="#" class="nav-link">Gift card</a>
            </div>
          </div>

          <!-- Products -->
          <div class="nav-section">
            <h3 class="nav-title">Products</h3>
            <div class="nav-links">
              <a href="#" class="nav-link">Furniture</a>
              <a href="#" class="nav-link">Decoration</a>
              <a href="#" class="nav-link">Storage</a>
              <a href="#" class="nav-link">Baby and child</a>
              <a href="#" class="nav-link">Connected home</a>
            </div>
          </div>

          <!-- Rooms -->
          <div class="nav-section">
            <h3 class="nav-title">Rooms</h3>
            <div class="nav-links">
              <a href="#" class="nav-link">Living room</a>
              <a href="#" class="nav-link">Dining room</a>
              <a href="#" class="nav-link">Cooked</a>
              <a href="#" class="nav-link">Bedroom</a>
              <a href="#" class="nav-link">Bathroom</a>
              <a href="#" class="nav-link">Office</a>
              <a href="#" class="nav-link">Laundry</a>
              <a href="#" class="nav-link">Garage</a>
            </div>
          </div>

          <!-- Planet -->
          <div class="nav-section">
            <h3 class="nav-title">We respect our planet</h3>
            <div class="planet-content">
              <img src="@/assets/Pic.png" alt="Interior design" class="planet-image" />
              <p class="planet-text">
                We're taking positive steps to reduce our impact on the planet. For us, that means retailing responsibly.
              </p>
              <a href="#" class="learn-more">Learn more ›</a>
            </div>
          </div>
        </div>
      </nav>

      <!-- Social Icons -->
      <div class="social-networks">
        <a href="#" class="social-icon"><img src="/assets/Facebook.svg" alt="Facebook"></a>
        <a href="#" class="social-icon"><img src="/assets/Twitter.svg" alt="Twitter"></a>
        <a href="#" class="social-icon"><img src="/assets/Linkedin.svg" alt="LinkedIn"></a>
        <a href="#" class="social-icon"><img src="/assets/Instagram.svg" alt="Instagram"></a>
      </div>

      <!-- Footer -->
      <div class="footer-bottom">
        <span class="copyright">© 2021 Agence Dnd</span>
        <div class="footer-links">
          <a href="#" class="footer-link">Privacy policy</a>
          <a href="#" class="footer-link">Term of service</a>
          <a href="#" class="footer-link">Language</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #F3EEE8;
  padding: 70px 80px 40px;
}

.content {
  max-width: 1440px;
  margin: 0 auto;
}

.navigation {
  display: flex;
  gap: 120px;
}

.logotype {
  font-family: 'Merriweather';
  font-weight: 700;
  font-size: 34px;
  line-height: 30px;
  color: #534B42;
}

.nav-sections {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 40px;
  flex: 1;
}

.nav-title {
  font-family: 'Varta';
  font-weight: 600;
  font-size: 25px;
  line-height: 30px;
  color: #534B42;
  margin-bottom: 24px;
}

.nav-links {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.nav-link {
  font-family: 'Varta';
  font-size: 18px;
  line-height: 25px;
  color: #706458;
  text-decoration: none;
}

.planet-image {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 4px;
  margin: 16px 0;
}

.planet-text {
  font-family: 'Varta';
  font-size: 16px;
  line-height: 25px;
  color: #706458;
  margin-bottom: 16px;
}

.learn-more {
  font-family: 'Karla';
  font-weight: 700;
  font-size: 17px;
  color: #A06056;
  text-decoration: none;
}

.social-networks {
  display: flex;
  justify-content: center;
  gap: 24px;
  margin: 60px 0;
}

.social-icon {
  width: 32px;
  height: 32px;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 20px;
  border-top: 1px solid rgba(112, 100, 88, 0.2);
}

.copyright {
  font-family: 'Varta';
  font-size: 18px;
  color: rgba(112, 100, 88, 0.7);
}

.footer-links {
  display: flex;
  gap: 30px;
}

.footer-link {
  font-family: 'Varta';
  font-size: 18px;
  color: rgba(112, 100, 88, 0.7);
  text-decoration: none;
}

@media (max-width: 1024px) {
  .footer {
    padding: 40px 40px 20px;
  }
  
  .navigation {
    flex-direction: column;
    gap: 40px;
  }

  .nav-sections {
    display: flex;
    flex-direction: column;
    gap: 40px;
  }
  .nav-section {
    width: 100%;
  }

  .planet-image,
  .planet-text {
    max-width: 400px;
  }

  .social-networks {
    justify-content: flex-start;
  }

  .footer-bottom {
    padding-top: 20px;
  }
}

@media (max-width: 640px) {
  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
    gap: 20px;
  }

  .footer-links {
    flex-direction: column;
    gap: 12px;
  }
}
</style>