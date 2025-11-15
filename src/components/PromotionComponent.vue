<template>
  <div class="promo" :style="{ backgroundColor: color }">
    <div class="promo-content">
      <h3 class="promo-title">{{ title }}</h3>
      <a :href="url" class="promo-link">
        <button
          class="shopbtn"
          :style="{ backgroundColor: buttonColor }"
          @click="shopNow"
        >
          Shop Now
        </button>
      </a>
    </div>

    <img class="promo-image" :src="image" :alt="title" />
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    color: String,
    image: String,
    buttonColor: String,
    url: String,
  },
  methods: {
    shopNow() {
      alert("Let's shop: " + this.title);
    },
  },
};
</script>

<style>
.promo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 35px;
  border-radius: 10px;
  box-sizing: border-box;
  width: 512px;
  height: 300px;
}

.promo-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  gap: 16px;
  flex: 1 1 50%;
  padding-right: 16px;
}

.promo-title {
  font-family: Quicksand, sans-serif;
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
  color: #253d4e;
  margin: 0;
}

.promo-image {
  width: 45%;
  height: 100%;
  object-fit: contain;
  border-radius: 6px;
}

.shopbtn {
  background-color: #3bb77e;
  width: 110px;
  height: 36px;
  border-radius: 4px;
  color: #ffffff;
  border: none;
  padding: 0 12px;
}
.shopbtn:hover {
  background-color: #36a66c;
  cursor: pointer;
}
</style>
