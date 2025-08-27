<template>
  <div class="blog-item">
    <img :src="image" :alt="title" class="blog-image">
    <div class="blog-content">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BlogPost',
  props: {
    title: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.blog-item {
  display: flex;
  margin-bottom: 30px;
  gap: 20px;
}

.blog-image {
  width: 500px;
  height: 120px;
  object-fit: cover;
  border-radius: 8px;
}

.blog-content {
  flex: 1;
}

.blog-content h3 {
  font-size: 2.5vh;
  margin-bottom: 10px;
}

.blog-content p {
  font-size: 1.5vh;
  line-height: 1.6;
  color: #555;
}
</style>
