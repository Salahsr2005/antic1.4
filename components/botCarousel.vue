<template>
  <section class="trends-section">
    <div class="container">
      <div class="header">
        <div class="title-group">
          <h2 class="title">Be aware of the latest trends</h2>
          <p class="subtitle">
            Stay informed of new trends, but also of our various offers.
          </p>
          <a href="#" class="learn-more">Learn more ›</a>
        </div>
        <div class="subscription">
          <input
            type="email"
            placeholder="email@address.com"
            class="email-input"
          />
          <button class="subscribe-btn">Subscribe</button>
        </div>
      </div>

      <div class="inspiration-section">
        <div class="carousel">
          <div
            class="carousel-content"
            :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
          >
            <!-- Slide 1 -->
            <div class="carousel-item">
              <div class="image-container">
                <img src="/assets/image3.svg" alt="Chair" />
              </div>
            </div>

            <!-- Slide 2 -->

            <!-- Slide 3 -->
            <div class="carousel-item">
              <div class="image-container">
                <img src="/assets/image4.svg" alt="Living room" />
               
              </div>
            </div>

            <!-- Slide 4 -->
            <div class="carousel-item">
              <div class="image-container">
                <img src="/assets/image1.svg" alt="Tables" />
                
              </div>
            </div>

            <!-- Slide 5 -->
            <div class="carousel-item">
              <div class="image-container">
                <img src="/assets/image2.svg" alt="Decoration" />
              </div>
            </div>
          </div>

          <div class="carousel-nav">
            <div class="inspiration-header">
              <h3 class="inspiration-title">Inspirations</h3>
            </div>
            <p class="inspiration-text">
              Our experts are keen to stay on top of trends in order to offer
              you new inspirations for your interior and exterior every day.
              Remember that to inspire you we have to inspire ourselves and we
              want to share that with you.
            </p>
            <div class="takeittop">
                <button
                @click="prevSlide"
                class="nav-btn prev"
                :disabled="currentSlide === 0"
              >
                <svg
                  width="40"
                  height="40"
                  viewBox="0 0 40 40"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <rect
                    x="-1"
                    y="1"
                    width="38"
                    height="38"
                    rx="19"
                    transform="matrix(-1 0 0 1 38 0)"
                    fill="white"
                  />
                  <rect
                    x="-1"
                    y="1"
                    width="38"
                    height="38"
                    rx="19"
                    transform="matrix(-1 0 0 1 38 0)"
                    stroke="#A06056"
                    stroke-width="2"
                  />
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M22.7929 12.2929C23.1834 11.9024 23.8166 11.9024 24.2071 12.2929C24.5976 12.6834 24.5976 13.3166 24.2071 13.7071L17.9142 20L24.2071 26.2929C24.5976 26.6834 24.5976 27.3166 24.2071 27.7071C23.8166 28.0976 23.1834 28.0976 22.7929 27.7071L15.7929 20.7071C15.4024 20.3166 15.4024 19.6834 15.7929 19.2929L22.7929 12.2929Z"
                    fill="#A06056"
                  />
                </svg>
              </button>
              <button @click="nextSlide" class="nav-btn next">
                <svg
                  width="40"
                  height="40"
                  viewBox="0 0 40 40"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <rect x="1" y="1" width="38" height="38" rx="19" fill="white" />
                  <rect
                    x="1"
                    y="1"
                    width="38"
                    height="38"
                    rx="19"
                    stroke="#A06056"
                    stroke-width="2"
                  />
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M17.2071 12.2929C16.8166 11.9024 16.1834 11.9024 15.7929 12.2929C15.4024 12.6834 15.4024 13.3166 15.7929 13.7071L22.0858 20L15.7929 26.2929C15.4024 26.6834 15.4024 27.3166 15.7929 27.7071C16.1834 28.0976 16.8166 28.0976 17.2071 27.7071L24.2071 20.7071C24.5976 20.3166 24.5976 19.6834 24.2071 19.2929L17.2071 12.2929Z"
                    fill="#A06056"
                  />
                </svg>
              </button>
              <div class="slide-counter">
                {{ String(currentSlide + 1).padStart(2, "0") }} /
                {{ String(totalSlides).padStart(2, "0") }}
              </div>

            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "TrendsCarousel",
  data() {
    return {
      currentSlide: 0,
      totalSlides: 2,
    };
  },
  methods: {
    nextSlide() {
      if (this.currentSlide < this.totalSlides - 1) {
        this.currentSlide++;
      }
    },
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      }
    },
  },
};
</script>

<style scoped>
.trends-section {
  padding: 64px 150px;
  background: #ffffff;
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;
  box-sizing: border-box;
}

.container {
  max-width: 1140px;
  margin: 0 auto;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 64px;
}

.title-group {
  max-width: 570px;
}

.title {
  font-family: "Merriweather", serif;
  font-size: 40px;
  line-height: 60px;
  font-weight: 400;
  color: #706458;
  margin: 0 0 24px 0;
  letter-spacing: -0.6px;
}

.subtitle {
  font-family: "Varta", sans-serif;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  margin: 0 0 16px 0;
}

.learn-more {
  font-family: 'Karla';
  font-weight: 700;
  font-size: 17px;
  color: #A06056;
  text-decoration: none;
}

.subscription {
  display: flex;
  flex-direction: row;
  gap: 0px;
  width: 360px;
}


.email-input {
  width: 70%; /* Adjust this value based on your needs */
  height: 48px;
  padding: 0 16px;
  border: 1px solid rgba(112, 100, 88, 0.3);
  background: #ffffff;
  font-family: "Varta", sans-serif;
  font-size: 16px;
  color: #706458;
}

.subscribe-btn {
  width: 30%; /* Adjust this value based on your needs */
  height: 48px;
  background: #706458;
  color: #ffffff;
  border: none;
  font-family: "Karla", sans-serif;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
}

.inspiration-section {
  margin-top: 64px;
}

.inspiration-header {
  margin-bottom: 48px;
  max-width: 570px;
}

.inspiration-title {
  font-family: "Merriweather", serif;
  font-size: 55px;
  line-height: 60px;
  color: #706458;
  margin: 0 10 75px 0px;
  font-weight: 400;
}

.inspiration-text {
  font-family: "Varta", sans-serif;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  margin: 0;
  margin-top: 40px;
  margin-left: 30px;
  margin-right: 226px;
  max-width: 359px;
  justify-content: center;
}
.takeittop{
    margin-top:-100px ;
    
}
.carousel {
  position: relative;
  overflow: hidden;
}

.carousel-content {
  display: flex;
  transition: transform 0.3s ease-in-out;
}

.carousel-item {
  min-width: calc(33.333% - 21.33px);
  margin-right: 32px;
}

.carousel-item:last-child {
  margin-right: 0;
}

.image-container {
  position: relative;
}

.image-container img {
  width: 100%;
  height: 550px;
  object-fit: cover;
}

.label {
  display: block;
  margin-top: 16px;
  font-family: "Varta", sans-serif;
  font-size: 18px;
  line-height: 25px;
  color: #706458;
}

.carousel-nav {
  display: flex;
  align-items: center;
  gap: 32px;
  margin-top: 0px;
}

.nav-btn {
  background: none;
  border: none;
  cursor: pointer;
  padding: 10px;
  
}

.nav-btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.slide-counter {
    position: absolute;
    right: 170px;
    bottom:95px ;
  width: 50px;
  height: 25px;
  font-family: "Varta";
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  opacity: 0.5;
  flex: none;
  order: 1;
  flex-grow: 0;
}
@media (max-width: 1440px) {
.takeittop {
  position: absolute;
  right: 0;
margin-top: -20px;
}
.slide-counter{
position: absolute;
right: 0;
}
}
@media (max-width: 1024px) {
  .trends-section {
    padding: 48px 40px;
  }

  .header {
    flex-direction: column;
    gap: 32px;
  }

  .subscription {
    width: 100%;
  }
  .takeittop {
    display: none;
    visibility: hidden;
  }
  .carousel-item {
    min-width: calc(50% - 16px);
  }
}

@media (max-width: 768px) {
  .trends-section {
    padding: 32px 20px;
  }

  .title {
    font-size: 40px;
    line-height: 45px;
  }

  .inspiration-title {
    font-size: 40px;
    line-height: 45px;
    margin-bottom: 0px; /* Reduced margin for mobile */
  }

  .inspiration-text {
    margin: 0 0 32px 0; /* Adjust margins for mobile */
    max-width: 100%; /* Full width on mobile */
  }

  /* Restructure carousel for grid layout */
  .carousel {
    overflow: visible; /* Allow content to be visible */
  }

  .carousel-content {
    display: grid;
    grid-template-columns: repeat(2, 1fr); /* 2 columns */
    gap: 20px; /* Space between items */
    transform: none !important; /* Prevent horizontal scrolling */
  }

  .carousel-item {
    min-width: unset;
    margin-right: 0;
    width: 100%;
  }

  .image-container {
    position: relative;
    width: 100%;
  }

  .image-container img {
    height: 200px; /* Smaller height for mobile */
    width: 100%;
    object-fit: cover;
  }

  /* Hide navigation on mobile since we're showing all images */
  .takeittop {
    display: none;
    visibility: hidden;
  }

  /* Adjust header section */
  .inspiration-section {
    margin-top: 32px;
  }

  .inspiration-header {
    margin-bottom: 24px;
  }

  /* Center text content */
  .carousel-nav {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 32px;
  }

  .slide-counter {
    display: none; /* Hide counter since we're showing all images */
  }
}

/* Add a slightly larger breakpoint for medium-sized devices */
@media (min-width: 769px) and (max-width: 1024px) {
  .carousel-content {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
  }

  .carousel-item {
    min-width: unset;
    margin-right: 0;
  }

  .image-container img {
    height: 300px;
  }
}
</style>
/* Picture */

position: absolute;
width: 600px;
height: 899.89px;
left: 79px;
top: -333px;

background: url(jean-philippe-delberghe-feijc-nqWKM-unsplash.jpg);
