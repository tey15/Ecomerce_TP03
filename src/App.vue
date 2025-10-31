<template>
  <div id="app" class="container">
    <h1>This is my first VueJs project</h1>

    <HeroSection
      :title="hero.title"
      :subtitle="hero.subtitle"
      :image="hero.image"
    />

    <div class="cards-row">
      <InfoCard
        v-for="card in cards"
        :key="card.id"
        :title="card.title"
        :description="card.description"
        :image="card.image"
        :bgColor="card.bgColor"
      />
    </div>
    <ActionBar :actions="actions" />

        <!-- ✅ New Promo Section -->
    <div class="promo-section">
      <PromoBanner
        v-for="promo in promos"
        :key="promo.id"
        :title="promo.title"
        :subtitle="promo.subtitle"
        :image="promo.image"
        :bgColor="promo.bgColor"
      />
    </div>
  </div>
  
</template>

<script setup>
import { ref } from 'vue'
import HeroSection from './components/HeroSection.vue'
import InfoCard from './components/InfoCard.vue'
// import ActionBar from './components/ActionBar.vue'
import PromoBanner from './components/PromoBanner.vue'

const hero = ref({
  title: 'Welcome to Vue Practice',
  
  subtitle: 'Build components and reuse them',
})

const cards = ref([
  { id: 1, title: 'Cake & Milk', description: 'First card description', image: '/images/image1.png', bgColor: '#FDE68A' },
  { id: 2, title: 'Peach', description: 'Second card description', image: '/images/image2.jpg', bgColor: '#BFDBFE' },
  { id: 3, title: 'Oganic Kiwi', description: 'Third card description', image: '/images/image3.jpg', bgColor: '#C7F9CC' },
  { id: 4, title: 'Red Apple', description: '68 items', image: '/images/image4.png', bgColor: '#FFECEC' },
  { id: 5, title: 'Snack', description: '34 items', image: '/images/image5.png', bgColor: '#FFF9E0' },
  { id: 6, title: 'Black Plum', description: '25 items', image: '/images/image6.png', bgColor: '#F9E6FF' },
  { id: 7, title: 'Vegetables', description: '65 items', image: '/images/image7.png', bgColor: '#E8FFE8' },
  { id: 8, title: 'Headphone', description: '33 items', image: '/images/image8.png', bgColor: '#FFFBEA' },
  { id: 9, title: 'Cake & Milk', description: '54 items', image: '/images/image9.png', bgColor: '#F7FFF1' },
  { id: 10, title: 'Orange', description: '63 items', image: '/images/image10.png', bgColor: '#FFF0F0' }
])

const promos = ref([
  {
    id: 1,
    title: 'Everyday Fresh & Clean with Our Products',
    subtitle: '',
    image: '/images/pomo1.png',
    bgColor: '#FFF8E1'
  },
  {
    id: 2,
    title: 'Make your Breakfast Healthy and Easy',
    subtitle: '',
    image: '/images/pomo2.png',
    bgColor: '#FFF1F3'
  },
  {
    id: 3,
    title: 'The best Organic Products Online',
    subtitle: '',
    image: '/images/pomo3.png',
    bgColor: '#F3F6FF'
  }
])

</script>

<style scoped>
 .container {
  /* max-width: 1200px; */
  width: 1590px;
  height: 185px;
  border: 1px;
  margin: 20px auto;
  padding: 12px;
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  margin-bottom: 18px;
  text-align: center;
}
.cards-row {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  /* gap: 18px; */
  gap: 43px;
  justify-items: center;
  margin: 40px 0;
}

.promo-section {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  margin-top: 40px;
  width: 1584px;
  height: 300px;
}
</style>
