<template>
  <div>
    <div class="categories">
      <!-- <h2>Categories</h2> -->
      <CategoryComponent
        v-for="(category, index) in categories"
        :key="index"
        :name="category.name"
        :product-count="category.productCount"
        :color="category.color"
        :image="category.image"
      />
    </div>

    <div class="promotions">
      <!-- <h2>Promotions</h2> -->
      <PromotionComponent
        v-for="(promo, index) in promotions"
        :key="index"
        :title="promo.title"
        :color="promo.color"
        :image="promo.image"
        :button-color="index < 2 ? '#43A047' : '#F59E0B'"
        :url="promo.url"
      />
    </div>
  </div>
</template>
<script>
import CategoryComponent from "./components/CategoryComponent.vue";
import PromotionComponent from "./components/PromotionComponent.vue";
export default {
  components: {
    CategoryComponent,
    PromotionComponent,
  },
  data() {
    return {
      categories: [
        {
          name: "Cake & Milk",
          productCount: 17,
          color: "#FDE68A",
          image: "/src/assets/images/image1.png",
        },
        {
          name: "Peach",
          productCount: 34,
          color: "#BFDBFE",
          image: "/src/assets/images/image2.jpg",
        },
        {
          name: "Oganic Kiwi",
          productCount: 23,
          color: "#C7F9CC",
          image: "/src/assets/images/image3.jpg",
        },
        {
          name: "Red Apple",
          productCount: 68,
          color: "#FFECEC",
          image: "/src/assets/images/image4.png",
        },
        {
          name: "Snack",
          productCount: 34,
          color: "#FFF9E0",
          image: "/src/assets/images/image5.png",
        },
        {
          name: "Black Plum",
          productCount: 25,
          color: "#F9E6FF",
          image: "/src/assets/images/image6.png",
        },
        {
          name: "Vegetables",
          productCount: 65,
          color: "#E8FFE8",
          image: "/src/assets/images/image7.png",
        },
        {
          name: "Headphone",
          productCount: 33,
          color: "#FFFBEA",
          image: "/src/assets/images/image8.png",
        },
        {
          name: "Cake & Milk",
          productCount: 54,
          color: "#F7FFF1",
          image: "/src/assets/images/image9.png",
        },
        {
          name: "Orange",
          productCount: 63,
          color: "#FFF0F0",
          image: "/src/assets/images/image10.png",
        },
      ],
      promotions: [
        {
          title: "Everyday Fresh & Clean with Our Products",
          color: "#FFF8E1",
          image: "/src/assets/images/pomo1.png",
          buttonColor: "#F59E0B",
          url: "/promotions/1",
        },
        {
          title: "Make Your Skin Healthy & Radiant",
          color: "#E1F5FE",
          image: "/src/assets/images/pomo2.png",
          buttonColor: "#0288D1",
          url: "/promotions/2",
        },
        {
          title: "The best Organic Products Onlines",
          color: "#E8F5E9",
          image: "/src/assets/images/pomo3.png",
          buttonColor: "#43A047",
          url: "/promotions/3",
        },
      ],
    };
  },
};
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
.categories {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  /* gap: 18px; */
  gap: 43px;
  justify-items: center;
  margin: 40px 5px;
}

/* .promotions{
  display: flex;
  justify-content: space-between;
  gap: 20px;
  margin-top: 40px;
  width: 1584px;
  height: 300px;
} */
.promotions {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  margin-top: 40px;
  width: 100%;
  max-width: 1584px;
  height: auto;
}
</style>
