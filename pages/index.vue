<template>
  <div class="home">
    <h2>歡迎來到我的電商網站</h2>
    <p>探索我們的精選商品，享受優質購物體驗！</p>
    <div class="cta-container">
      <NuxtLink to="/products" class="cta-button">瀏覽所有商品</NuxtLink>
    </div>

    <section class="featured-products">
      <h3>熱門產品</h3>
      <div class="product-grid">
        <div class="product-card" v-for="product in featuredProducts" :key="product.id">
          <img :src="product.image" :alt="product.name">
          <h4>{{ product.name }}</h4>
          <p>NT$ {{ product.price }}</p>
          <NuxtLink :to="`/products#${product.id}`" class="view-product">查看商品</NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const featuredProducts = ref([
  { id: 1, name: '時尚手錶', price: 2999, image: 'https://via.placeholder.com/200x200?text=Watch' },
  { id: 2, name: '智能手機', price: 15999, image: 'https://via.placeholder.com/200x200?text=Smartphone' },
  { id: 3, name: '無線耳機', price: 3999, image: 'https://via.placeholder.com/200x200?text=Earphones' },
]);
</script>

<style scoped>
.home {
  text-align: center;
  padding: 2rem 0;
}

h2 {
  color: var(--primary-color);
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

.cta-container {
  margin-bottom: 3rem;
}

.cta-button {
  display: inline-block;
  background-color: var(--secondary-color);
  color: white;
  padding: 0.8rem 1.5rem;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.cta-button:hover {
  background-color: #e67e22;
}

.featured-products {
  margin-top: 3rem;
}

h3 {
  color: var(--primary-color);
  font-size: 2rem;
  margin-bottom: 2rem;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  max-width: 800px;
  margin: 0 auto;
}

.product-card {
  background-color: white;
  border-radius: 8px;
  padding: 1rem;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-card img {
  max-width: 100%;
  border-radius: 4px;
  margin-bottom: 1rem;
}

.product-card h4 {
  margin: 0.5rem 0;
  color: var(--text-color);
}

.product-card p {
  color: var(--secondary-color);
  font-weight: bold;
  margin-bottom: 1rem;
}

.view-product {
  display: inline-block;
  background-color: var(--primary-color);
  color: white;
  padding: 0.5rem 1rem;
  text-decoration: none;
  border-radius: 4px;
  transition: background-color 0.3s ease;
}

.view-product:hover {
  background-color: #3a7bd5;
}
</style>