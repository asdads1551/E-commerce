<template>
  <div class="app-container">
    <header>
      <div class="header-content">
        <h1>我的電商網站</h1>
        <nav>
          <ul>
            <li><NuxtLink to="/">首頁</NuxtLink></li>
            <li><NuxtLink to="/products">商品</NuxtLink></li>
            <li><NuxtLink to="/cart">購物車</NuxtLink></li>
          </ul>
        </nav>
      </div>
    </header>

    <main>
      <NuxtPage />
    </main>

    <footer>
      <p>&copy; 2023 我的電商網站. 版權所有.</p>
    </footer>
  </div>
</template>

<script setup>
// 這裡可以添加需要的 Vue 3 組合式 API
</script>

<style>
:root {
  --primary-color: #4a90e2;
  --secondary-color: #f39c12;
  --background-color: #f4f4f4;
  --text-color: #333;
}

body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: var(--background-color);
  color: var(--text-color);
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  background-color: var(--primary-color);
  color: white;
  padding: 1rem 0;
}

.header-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1 {
  margin: 0;
  font-size: 1.5rem;
}

nav ul {
  list-style-type: none;
  padding: 0;
  display: flex;
}

nav ul li {
  margin-left: 1rem;
}

nav ul li a {
  color: white;
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s ease;
}

nav ul li a:hover {
  color: var(--secondary-color);
}

main {
  flex-grow: 1;
  padding: 2rem;
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
  box-sizing: border-box;
}

footer {
  background-color: var(--primary-color);
  color: white;
  text-align: center;
  padding: 1rem 0;
  margin-top: auto;
}
</style>
