<template>
  <section class="find-your-room">
    <div class="container">
      <h1 class="title">Find your room</h1>

      <div class="select-room">
        <p class="paragraph">
          Dining room, bedroom, bathroom or office. Find what you need
        </p>

        <div class="slider">
          <div
            class="slider-content"
            :style="{ transform: getSlideTransform() }"
          >
            <!-- Bedroom -->
            <div class="slider-item">
              <div class="item-group">
                <div class="background">
                  <div class="mask">
                    <img
                      src="/assets/image2.svg"
                      alt="Bedroom"
                      class="picture"
                    />
                  </div>
                </div>
                <div class="content">
                  <span class="label">News arrivals</span>
                  <h2 class="item-title">Bedroom</h2>
                </div>
              </div>
            </div>

            <!-- Living room -->
            <div class="slider-item">
              <div class="item-group">
                <div class="background">
                  <div class="mask">
                    <img
                      src="/assets/image1.svg"
                      alt="Living room"
                      class="picture"
                    />
                  </div>
                </div>
                <div class="content">
                  <span class="label">News arrivals</span>
                  <h2 class="item-title">Living room</h2>
                </div>
              </div>
            </div>

            <!-- Dining room -->
            <div class="slider-item">
              <div class="item-group">
                <div class="background">
                  <div class="mask">
                    <img
                      src="/assets/image4.svg"
                      alt="Dining room"
                      class="picture"
                    />
                  </div>
                </div>
                <div class="content">
                  <span class="label">News arrivals</span>
                  <h2 class="item-title">Dining room</h2>
                </div>
              </div>
            </div>

            <!-- Bathroom -->
            <div class="slider-item">
              <div class="item-group">
                <div class="background">
                  <div class="mask">
                    <img
                      src="/assets/image3.svg"
                      alt="Bathroom"
                      class="picture"
                    />
                  </div>
                </div>
                <div class="content">
                  <span class="label">News arrivals</span>
                  <h2 class="item-title">Bathroom</h2>
                </div>
              </div>
            </div>

            <!-- Office -->
            <div class="slider-item">
              <div class="item-group">
                <div class="background">
                  <div class="mask">
                    <img
                      src="/assets/image5.svg"
                      alt="Office"
                      class="picture"
                    />
                  </div>
                </div>
                <div class="content">
                  <span class="label">News arrivals</span>
                  <h2 class="item-title" style="margin-left: 70px;">Office</h2>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="slider-nav">
        <div class="dots">
          {{ String(currentSlide + 1).padStart(2, "0") }} /
          {{ String(totalSlides).padStart(2, "0") }}
        </div>
        <div class="nav">
          <button @click="nextSlide" class="next">
            Next
            <svg width="9" height="16" viewBox="0 0 9 16" fill="none">
              <path d="M1 1L8 8L1 15" stroke="#A06056" stroke-width="2" />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "RoomCarousel",
  data() {
    return {
      currentSlide: 0,
      totalSlides: 5,
      slideWidth: 458.25,
      slideGap: 32,
    };
  },
  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.totalSlides;
    },
    getSlideTransform() {
      return `translateX(-${
        this.currentSlide * (this.slideWidth + this.slideGap)
      }px)`;
    },
  },
};
</script>

<style scoped>
.find-your-room {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 64px 0 70px;
  background: #f3eee8;
  width: 100%;
}

.container {
  width: 100%;
  max-width: 1440px;
  padding: 0 150px;
  box-sizing: border-box;
}

.title {
  width: 1140px;
  height: 60px;
  font-family: "Merriweather", serif;
  font-style: normal;
  font-weight: 400;
  font-size: 55px;
  line-height: 60px;
  letter-spacing: -0.6px;
  color: #706458;
  margin: 0 0 48px 0;
}

.select-room {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  padding: 0;
  gap: 24px;
  width: 1140px;
  height: 350px;
  margin-bottom: 48px;
}

.paragraph {
  width: 165px;
  height: 100px;
  font-family: "Varta", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  margin: 0;
}

.slider {
  width: 947.5px;
  height: 350px;
  overflow: hidden;
  position: relative;
}

.slider-content {
  display: flex;
  gap: 32px;
  transition: transform 0.3s ease-in-out;
  position: absolute;
}

.slider-item {
  width: 458.25px;
  height: 350px;
  flex-shrink: 0;
}

.item-group {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  padding: 0;
  gap: 32px;
  position: relative;
  width: 458.25px;
  height: 350px;
}

.background {
  width: 570.25px;
  height: 350px;
  position: relative;
}

.mask {
  position: absolute;
  left: 0%;
  right: 42.99%;
  top: 0%;
  bottom: 0%;
  background: #F3EEE8;
  border-radius: 1px;
  overflow: hidden;
}

.picture {
  width: 458.25px;
  height: 350px;
  object-fit: cover;
}

.content {
  position: absolute;
  left: calc(261.25px + 32px);
  top: 0;
}

.label {
  display: block;
  width: 165px;
  height: 25px;
  font-family: "Varta", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  margin-bottom: 0px;
  margin-top: 20px;
}

.item-title {
  position: absolute;
  height: 430px;
  left: -99.27%;
  right: 52.93%;
  top: calc(200% - 330px / 2);
  font-family: "Merriweather";
  font-style: normal;
  font-weight: 400;
  font-size: 55px;
  line-height: 60px;
  display: flex;
  align-items: center;
  text-align: center;
  letter-spacing: -0.6px;
  color: #a06056;
}

.slider-nav {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  padding: 0;
  gap: 30px;
  width: 1140px;
  height: 25px;
}

.dots {
  width: 165px;
  height: 25px;
  font-family: "Varta", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 25px;
  color: rgba(112, 100, 88, 0.9);
  opacity: 0.5;
}

.nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0;
  gap: 16px;
  width: 945px;
  height: 25px;
}

.next {
  display: flex;
  align-items: center;
  gap: 16px;
  font-family: "Karla", sans-serif;
  font-style: normal;
  font-weight: 700;
  font-size: 20px;
  line-height: 25px;
  letter-spacing: 0.3px;
  color: #a06056;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
}

@media (max-width: 1440px) {
  .container {
    padding: 0 5%;
  }

  .title,
  .select-room,
  .slider-nav {
    width: 100%;
  }

  .slider {
    width: calc(100% - 165px - 24px);
  }

  .slider-item {
    width: calc(50% - 16px);
  }

  .item-group {
    width: 100%;
  }

  .background {
    width: 60%;
  }
}

@media (max-width: 768px) {
  .find-your-room {
    padding: 32px 0;
    overflow: hidden;
  }

  .container {
    padding: 0 20px;
  }

  .title {
    width: 100%;
    font-size: 40px;
    line-height: 45px;
    margin-bottom: 24px;
  }

  .select-room {
    flex-direction: column;
    height: auto;
    width: 100%;
    gap: 24px;
  }

  .paragraph {
    width: 100%;
    height: auto;
    margin-bottom: 20px;
  }

  .slider {
    width: 100%;
    height: 350px;
    overflow: visible;
  }

  .slider-content {
    display: flex;
    gap: 32px;
    transition: transform 0.3s ease-in-out;
    width: max-content;
  }

  .slider-item {
    width: 458.25px;
    height: 350px;
    flex-shrink: 0;
  }

  .item-group {
    width: 458.25px;
    height: 350px;
    gap: 32px;
    overflow: visible;
  }

  .background {
    width: 458.25px;
    height: 350px;
  }

  .mask {
    right: 0;
    width: 100%;
  }

  .picture {
    width: 200.25px;
    height: 350px;
    object-fit: cover;
  }

  .content {
    position: absolute;
    left: 20px;
    top: auto;
    bottom: -60px;
  }

  .label {
    color: #706458;
    position: absolute;
    top: -400px;
    margin-top: 2px;
    margin-left: 200px;
    font-size: 18px;
  }

  .item-title {
    position: absolute;
    top: -300px;
    left: 120px;
    height: auto;
    font-size: 40px;
    line-height: 45px;
    text-align: left;
    color: #A06056;
  }

  .slider-nav {
    width: 100%;
    margin-top: 80px;
  }

  .nav {
    width: calc(100% - 195px);
  }
}
@media (min-width: 769px) and (max-width: 1440px) {
  .find-your-room {
    padding: 32px 0;
    overflow: hidden;
  }

  .container {
    padding: 0 20px;
  }

  .title {
    width: 100%;
    font-size: 40px;
    line-height: 45px;
    margin-bottom: 24px;
  }

  .select-room {
    flex-direction: column;
    height: auto;
    width: 100%;
    gap: 24px;
  }

  .paragraph {
    width: 100%;
    height: auto;
    margin-bottom: 20px;
  }

  .slider {
    width: 100%;
    height: 350px;
    overflow: visible;
  }

  .slider-content {
    display: flex;
    gap: 32px;
    transition: transform 0.3s ease-in-out;
    width: max-content;
  }

  .slider-item {
    width: 458.25px;
    height: 350px;
    flex-shrink: 0;
  }

  .item-group {
    width: 458.25px;
    height: 350px;
    gap: 32px;
    overflow: visible;
  }

  .background {
    width: 458.25px;
    height: 350px;
  }

  .mask {
    right: 0;
    width: 100%;
  }

  .picture {
    width: 200.25px;
    height: 350px;
    object-fit: cover;
  }

  .content {
    position: absolute;
    left: 20px;
    top: auto;
    bottom: -60px;
  }

  .label {
    color: #706458;
    position: absolute;
    top: -400px;
    margin-top: 2px;
    margin-left: 200px;
    font-size: 18px;
  }

  .item-title {
    position: absolute;
    top: -300px;
    left: 120px;
    height: auto;
    font-size: 40px;
    line-height: 45px;
    text-align: left;
    color: #A06056;
  }

  .slider-nav {
    width: 100%;
    margin-top: 80px;
  }

  .nav {
    width: calc(100% - 195px);
  }
}
</style>
