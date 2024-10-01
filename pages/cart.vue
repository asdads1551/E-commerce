<template>
  <div class="cart">
    <h2>購物車</h2>
    <div v-if="cartItems.length === 0" class="empty-cart">
      <p>您的購物車是空的</p>
      <NuxtLink to="/products" class="continue-shopping">繼續購物</NuxtLink>
    </div>
    <div v-else class="cart-items">
      <div class="cart-item" v-for="(item, index) in cartItems" :key="index">
        <img src="https://via.placeholder.com/100" alt="Product Image">
        <div class="item-details">
          <h3>{{ item.name }}</h3>
          <p>NT$ {{ item.price }}</p>
        </div>
        <button class="remove-item">移除</button>
      </div>
      <div class="cart-total">
        <h3>總計: NT$ {{ cartTotal }}</h3>
        <button class="checkout-button">結帳</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const cartItems = ref([
  { name: '商品 1', price: 100 },
  { name: '商品 2', price: 200 },
]);

const cartTotal = computed(() => {
  return cartItems.value.reduce((total, item) => total + item.price, 0);
});
</script>

<style scoped>
.cart {
  padding: 2rem 0;
}

h2 {
  color: var(--primary-color);
  font-size: 2rem;
  margin-bottom: 2rem;
  text-align: center;
}

.empty-cart {
  text-align: center;
}

.continue-shopping {
  display: inline-block;
  background-color: var(--secondary-color);
  color: white;
  padding: 0.8rem 1.5rem;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  margin-top: 1rem;
}

.cart-items {
  background-color: white;
  border-radius: 8px;
  padding: 1rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.cart-item {
  display: flex;
  align-items: center;
  padding: 1rem 0;
  border-bottom: 1px solid #eee;
}

.cart-item img {
  width: 80px;
  height: 80px;
  object-fit: cover;
  margin-right: 1rem;
}

.item-details {
  flex-grow: 1;
}

.remove-item {
  background-color: #e74c3c;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
}

.cart-total {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 2rem;
}

.checkout-button {
  background-color: var(--primary-color);
  color: white;
  border: none;
  padding: 0.8rem 1.5rem;
  border-radius: 5px;
  font-weight: bold;
  cursor: pointer;
}
</style>