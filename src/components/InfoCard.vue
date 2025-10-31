<template>
  <article class="card" :style="{ backgroundColor: bgColor || '#fff' }">
    <img v-if="image" :src="image" class="card-image" />
    <div class="card-body">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </article>
</template>

<script setup lang="ts">
defineProps({
  title: { type: String, default: '' },
  description: { type: String, default: '' },
  image: { type: String, default: '' },
  bgColor: { type: String, default: '' }
})
</script>

<style scoped>

 .card {
  width: 136px;
  height: 185px;
  border: 1px;
  border-radius: 16px;
  padding: 10px;
  text-align: center;
  box-shadow: 0 2px 6px rgba(0,0,0,0.08);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
}
.card-image {
  width: 120px;
  height: 120px;
  top: -116px;
  left: 41px;
  object-fit: contain;
  margin: 0 auto 8px auto;
}

.card-body {
  text-align: center;
}

.card-body h3 {
  font-size: 16px;
  font-weight: 700;
  height: 20px;
  margin: 4px 0 2px;
}

.card-body p {
  /* font-size: 12px;
  color: #555; */
  font-family: loto, sans-serif;
  font-weight: 400;
  font-size: 12px;
  line-height: 18px;
  letter-spacing: 0%;
  text-align: center;
  color: #B6B6B6;
}
</style>
