<template>
  <div class="blog-page">
    <!-- 页面标题 -->
    <div class="page-header">
      <h1>博客</h1>
    </div>

    <!-- 博客列表 -->
    <div class="blog-list">
      <BlogPost
        v-for="(blog, index) in blogs"
        :key="index"
        :title="blog.title"
        :image="blog.image"
        :description="blog.description"
        :date="blog.date"
        :author="blog.author"
        :tags="blog.tags"
        class="blog-post-full"
      />
    </div>
  </div>
</template>

<script>
import BlogPost from '@/components/BlogPost.vue'
import { blogs } from '@/data.js'

export default {
  name: 'Blog',
  components: {
    BlogPost
  },
  data() {
    return {
      blogs: blogs
    }
  }
}
</script>

<style scoped>
.blog-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.page-header {
  margin-bottom: 30px;
  text-align: center;
}

.page-header h1 {
  font-size: 3vh;
  color: #333;
  border-bottom: 2px solid #E1BE97;
  padding-bottom: 10px;
  display: inline-block;
}

.blog-list {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.blog-post-full {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  padding: 20px;
}
</style>
