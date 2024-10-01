<template>
  <div class="products">
    <h2>商品列表</h2>
    <div class="product-grid">
      <div class="product-card" v-for="product in products" :key="product.id">
        <img :src="product.image" :alt="product.name">
        <h3>{{ product.name }}</h3>
        <p>NT$ {{ product.price }}</p>
        <button @click="addToCart(product)">加入購物車</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const products = ref([
  { id: 1, name: '時尚手錶', price: 2999, image: 'https://via.placeholder.com/200x200?text=Watch' },
  { id: 2, name: '智能手機', price: 15999, image: 'https://via.placeholder.com/200x200?text=Smartphone' },
  { id: 3, name: '無線耳機', price: 3999, image: 'https://via.placeholder.com/200x200?text=Earphones' },
  { id: 4, name: '筆記型電腦', price: 29999, image: 'https://via.placeholder.com/200x200?text=Laptop' },
  { id: 5, name: '運動鞋', price: 2499, image: 'https://via.placeholder.com/200x200?text=Sneakers' },
  { id: 6, name: '太陽眼鏡', price: 1299, image: 'https://via.placeholder.com/200x200?text=Sunglasses' },
]);

const addToCart = (product) => {
  // 這裡可以添加將商品加入購物車的邏輯
  console.log(`已將 ${product.name} 加入購物車`);
  // 在實際應用中，您可能需要使用 Vuex 或 Pinia 來管理購物車狀態
};
</script>

<style scoped>
.products {
  padding: 2rem 0;
}

h2 {
  color: var(--primary-color);
  font-size: 2rem;
  margin-bottom: 2rem;
  text-align: center;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 2rem;
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

.product-card h3 {
  margin: 0.5rem 0;
  color: var(--text-color);
}

.product-card p {
  color: var(--secondary-color);
  font-weight: bold;
  margin-bottom: 1rem;
}

.product-card button {
  background-color: var(--primary-color);
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.product-card button:hover {
  background-color: #3a7bd5;
}
</style>