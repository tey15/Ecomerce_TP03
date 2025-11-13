<template>
  <article class="card" :style="{ backgroundColor: color || '#fff' }">
    <img v-if="image" :src="image" class="card-image" />
    <div class="card-body">
      <h3>{{ name }}</h3>
      <p>{{ productCount }} products</p>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    name: String,
    productCount: Number,
    color: String,
    image: String
  }
};
</script>

<style scoped>
.card {
  width: 136px;
  height: 185px;
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
  object-fit: contain;
  margin: 0 auto 8px auto;
}

.card-body h3 {
  font-size: 16px;
  font-weight: 700;
  margin: 4px 0 2px;
}

.card-body p {
  font-family: Lato, sans-serif;
  font-weight: 400;
  font-size: 12px;
  color: #B6B6B6;
}
</style>
