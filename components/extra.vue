<template>
  <section class="design-services">
    <div class="left-column">
      <h2 class="main-title">We stay by your side to design your projects</h2>
      <a href="#" class="find-more">Find out more ›</a>
    </div>

    <div class="services-grid">
      <div class="service-card">
        <h3 class="service-title">Our Advices</h3>
        <p class="service-description">
          What if you took advantage of this rather special period to rethink
          your interior? You spend more time at home so you might as well feel
          good there.
        </p>
      </div>

      <div class="service-card">
        <h3 class="service-title">Click and Collect</h3>
        <p class="service-description">
          Adapted and contactless. Free from € 200 of purchases in stores
          offering the service.
        </p>
      </div>

      <div class="service-card">
        <h3 class="service-title">Conception Service</h3>
        <p class="service-description">
          Personalized service with an expert advisor for your interior and
          exterior decoration or layout projects.
        </p>
      </div>

      <div class="service-card">
        <h3 class="service-title">Installation Service</h3>
        <p class="service-description">
          Our furniture packaged in flat packs are designed for easy assembly.
          But you can call on our partner.
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "DesignServices",
};
</script>

<style scoped>
.design-services {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 48px;
  background: #f3eee8;
  padding: 64px 150px 70px;
}

.left-column {
  flex: 0 0 380px;
}

.main-title {
  font-family: "Merriweather", serif;
  font-size: 55px;
  line-height: 1.2;
  color: #706458;
  margin: 0 0 32px 0;
  font-weight: 400;
}

.find-more {
  font-family: 'Karla';
  font-weight: 700;
  font-size: 17px;
  color: #A06056;
  text-decoration: none;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 48px 32px;
  flex: 1;
}

.service-card {
  max-width: 380px;
}

.service-title {

font-family: 'Varta';
font-style: normal;
font-weight: 600;
font-size: 25px;
line-height: 30px;
letter-spacing: -0.2px;
color: #A06056;


}

.service-description {
  font-family: "Varta", sans-serif;
  color: #666666;
  font-size: 16px;
  line-height: 1.5;
  margin: 0;
  margin-top: 12px;
}

@media (max-width: 1024px) {
  .design-services {
    flex-direction: column;
    padding: 48px 24px;
  }

  .left-column {
    width: 100%;
    flex: none;
  }

  .main-title {
    font-size: 36px;
    margin-bottom: 24px;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 32px;
    width: 100%;
  }

  .service-card {
    max-width: 100%;
  }

  .service-title {
    font-size: 20px;
    margin-bottom: 12px;
  }
}
</style>
