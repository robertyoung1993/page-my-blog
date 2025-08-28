<template>
  <div class="home-container">
    <div class="hero-section">
      <h1>欢迎来到我的个人博客</h1>
      <p>在这里分享我的想法、经验和见解</p>
    </div>

    <div class="content-section">
      <!-- 我的笔记模块 -->
      <div class="module">
        <h2>我的笔记</h2>
        <div class="notes-container">
          <NoteCard 
            v-for="(note, index) in notes" 
            :key="index"
            :title="note.title"
            :date="note.date"
          />
        </div>
      </div>

      <!-- 最近的博客模块 -->
      <div class="module">
        <div class="module-header">
          <h2>最近博客</h2>
          <router-link to="/blog" class="view-all">查看全部</router-link>
        </div>
        <div class="blog-list">
          <BlogPost
            v-for="(blog, index) in recentBlogs"
            :key="index"
            :title="blog.title"
            :image="blog.image"
            :description="blog.description"
            :date="blog.date"
            :author="blog.author"
            :tags="blog.tags"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NoteCard from '@/components/NoteCard.vue'
import BlogPost from '@/components/BlogPost.vue'
import { notes, blogs } from '@/data.js'

export default {
  name: 'Home',
  components: {
    NoteCard,
    BlogPost
  },
  data() {
    return {
      notes: notes,
      blogs: blogs
    }
  },
  computed: {
    recentBlogs() {
      // 只显示前3篇博客
      return this.blogs.slice(0, 3);
    }
  }
}
</script>

<style scoped>
.home-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.hero-section {
  text-align: center;
  padding: 50px 0;
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  margin-bottom: 30px;
}

.hero-section h1 {
  font-size: 3.5vh;
  color: #333;
  margin-bottom: 20px;
}

.hero-section p {
  font-size: 2vh;
  color: #666;
}

.content-section {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.module {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.module-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.module-header h2 {
  font-size: 2.5vh;
  color: black;
}

.view-all {
  text-decoration: none;
  color: #664401;
  font-size: 1.5vh;
  padding: 5px 10px;
  border: 1px solid #E1BE97;
  border-radius: 5px;
  transition: all 0.3s ease;
}

.view-all:hover {
  background-color: #F9F4E9;
}

.notes-container {
  display: flex;
  gap: 40px;
}

.blog-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
