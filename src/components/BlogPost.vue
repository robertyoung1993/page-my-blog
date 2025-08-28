<template>
  <div class="blog-item">
    <img :src="image" :alt="title" class="blog-image">
    <div class="blog-content">
      <h3>{{ title }}</h3>
      <p class="blog-meta">{{ date }} | {{ author }}</p>
      <p>{{ description }}</p>
      <div class="blog-tags">
        <span v-for="(tag, index) in tags" :key="index" class="tag">{{ tag }}</span>
      </div>
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
    },
    date: {
      type: String,
      default: ''
    },
    author: {
      type: String,
      default: ''
    },
    tags: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>
.blog-item {
  display: flex;
  gap: 20px;
}

.blog-image {
  width: 300px;
  height: 150px;
  object-fit: cover;
  border-radius: 8px;
}

.blog-content {
  flex: 1;
}

.blog-content h3 {
  font-size: 2.5vh;
  margin-bottom: 10px;
  color: #333;
}

.blog-meta {
  font-size: 1.3vh;
  color: #777;
  margin-bottom: 10px;
}

.blog-content p {
  font-size: 1.5vh;
  line-height: 1.6;
  color: #555;
  margin-bottom: 15px;
}

/* 标签样式 */
.blog-tags {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.tag {
  background-color: #F9F4E9;
  color: #664401;
  padding: 5px 10px;
  border-radius: 15px;
  font-size: 1.2vh;
}
</style>
