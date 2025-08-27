<template>
  <div class="nav-menu">
    <div 
      v-for="(item, index) in items" 
      :key="index" 
      class="nav-item"
      @click="updatePage(index)"
      :style="{ fontWeight: currentPage === index ? 'bold' : 'normal' }"
    >
      {{ item }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navigation',
  props: {
    items: {
      type: Array,
      required: true
    },
    currentPage: {
      type: Number,
      required: true
    }
  },
  methods: {
    updatePage(index) {
      this.$emit('update-page', index)
    }
  }
}
</script>

<style scoped>
.nav-menu {
  padding: 20px 0;
}

.nav-item {
  padding: 10px 20px;
  font-size: 1.8vh;
  color: #555;
  cursor: pointer;
  transition: all 0.3s ease;
}

.nav-item:hover {
  color: #664401;
  font-weight: bold;
}
</style>
