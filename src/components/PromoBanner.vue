<template>
  <div class="promo-banner" :style="{ backgroundColor: bgColor }">
    <div class="promo-text">
      <h2>{{ title }}</h2>
      <p>{{ subtitle }}</p>
      <button class="shop-btn">Shop Now →</button>
    </div>
    <img :src="image" :alt="title" class="promo-image" />
  </div>
</template>

<script setup>
defineProps({
  title: String,
  subtitle: String,
  image: String,
  bgColor: String
})
</script>

<style scoped>
.promo-banner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 35px;
  border-radius: 10px;
  width: 100%;
  height: 220px;
  box-sizing: border-box;
  width: 512px;
  height: 300px;
}
/* .promo-text {
  max-width: 60%;
} */

.promo-text h2 {
    font-family: Quicksand, sans-serif;
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
  letter-spacing: -0.04%;
  color: #253D4E;

}

/* .promo-text p {
  font-size: 16px;
  color: #374151;
  margin-bottom: 12px;
} */

.shop-btn {
  background-color: #3BB77E;
  width: 109.83px;
  height: 31px;
  top: 190px;
  left: 48px;
  border-radius: 3px;
  color: #FFFFFF;
}

.shop-btn:hover {
  background-color: #16a34a;
}

.promo-image {
  height: 140px;
  object-fit: contain;
}
</style>
