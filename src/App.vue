<template>
  <div id="app">
    <div class="navigation">
      <router-link to="/" class="nav-link">首页</router-link>
      <router-link to="/blog" class="nav-link">博客</router-link>
      <router-link to="/about" class="nav-link">关于</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Arial', sans-serif;
  background-color: #f8f9fa;
  color: #333;
}

.navigation {
  background-color: #fff;
  padding: 20px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  display: flex;
  justify-content: center;
  gap: 30px;
}

.nav-link {
  text-decoration: none;
  color: #555;
  font-size: 1.8vh;
  padding: 10px 20px;
  border-radius: 5px;
  transition: all 0.3s ease;
}

.nav-link:hover {
  color: #664401;
  background-color: #f9f4e9;
}

.router-link-exact-active {
  font-weight: bold;
  color: #664401;
  background-color: #f9f4e9;
}
</style>
