<template>
  <div>
    <!-- Categories Section -->
    <div class="categories">
      <CategoryComponent
        v-for="(category, index) in categories"
        :key="index"
        :name="category.name"
        :product-count="category.productCount"
        :color="category.color"
        :image="category.image"
      />
    </div>

    <!-- Promotions Section -->
    <div class="promotions">
      <PromotionComponent
        v-for="(promo, index) in promotions"
        :key="index"
        :title="promo.title"
        :color="promo.color"
        :image="promo.image"
        :button-color="promo.buttonColor"
        :url="promo.url"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import CategoryComponent from "./components/CategoryComponent.vue";
import PromotionComponent from "./components/PromotionComponent.vue";

export default {
  components: {
    CategoryComponent,
    PromotionComponent,
  },

  data() {
    return {
      categories: [],
      promotions: [],
    };
  },

  methods: {
    // Fetch categories from backend
    fetchCategories() {
      axios
        .get("http://localhost:3000/api/categories")
        .then((res) => {
          this.categories = res.data.map((c) => ({
            ...c,
            image: `http://localhost:3000/${c.image.replace(/\\/g, "/")}`,
          }));
          console.log("Categories loaded:", this.categories);
        })
        .catch((err) => console.error("Error loading categories:", err));
    },

    // Fetch promotions from backend
    fetchPromotions() {
      axios
        .get("http://localhost:3000/api/promotions")
        .then((res) => {
          this.promotions = res.data.map((p) => ({
            ...p,
            image: `http://localhost:3000/${p.image.replace(/\\/g, "/")}`,
          }));
          console.log("Promotions loaded:", this.promotions);
        })
        .catch((err) => console.error("Error loading promotions:", err));
    },
  },

  mounted() {
    this.fetchCategories();
    this.fetchPromotions();
  },
};
</script>

<style scoped>
.categories {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 43px;
  justify-items: center;
  margin: 40px 5px;
}

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
