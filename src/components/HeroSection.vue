<template>
  <section class="hero">
    <!-- alt falls back to imageAlt prop, then title, then empty string for decorative images -->
    <img v-if="image" :src="image" :alt="imageAlt || title || ''" class="hero-image" />
    <div class="hero-text">
      <h2>{{ title }}</h2>
      <p>{{ subtitle }}</p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineProps({
  title: { type: String, default: '' },
  subtitle: { type: String, default: '' },
  image: { type: String, default: '' },
  // optional alt text for the hero image
  imageAlt: { type: String, default: '' }
})
</script>

<style scoped>
.hero {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 12px;
  border-radius: 8px;
  background: #f3f4f6;
}
.hero-image {
  width: 240px;
  height: 120px;
  object-fit: cover;
  border-radius: 6px;
}
.hero-text h2 {
  margin: 0;
}
</style>
