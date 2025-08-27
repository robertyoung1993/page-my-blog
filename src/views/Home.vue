<template>
  <div class="container">
    <!-- 左侧导航栏 -->
    <div class="left-column">
      <div class="blog-title">
        <h1>Pages专区</h1>
      </div>
      <Navigation :items="navItems" :current-page="currentPage" @update-page="setCurrentPage" />
    </div>

    <!-- 右侧内容区域 -->
    <div class="right-column">
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
        <h2>最近博客</h2>
        <BlogPost
          v-for="(blog, index) in blogs"
          :key="index"
          :title="blog.title"
          :image="blog.image"
          :description="blog.description"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from '@/components/Navigation.vue'
import NoteCard from '@/components/NoteCard.vue'
import BlogPost from '@/components/BlogPost.vue'
import { navItems, notes, blogs } from '@/data.js'

export default {
  name: 'Home',
  components: {
    Navigation,
    NoteCard,
    BlogPost
  },
  data() {
    return {
      currentPage: 0,
      navItems: navItems,
      notes: notes,
      blogs: blogs
    }
  },
  methods: {
    setCurrentPage(index) {
      this.currentPage = index
      console.log('当前页面:', this.navItems[index])
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  margin-top: 2.5vh;
  padding: 0 5vw;
}

.left-column {
  width: 15%;
  background-color: white;
  border-left: 3px solid #E1BE97;
  border-right: 1px solid #F9F4E9;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.blog-title {
  padding-left: 20%;
  font-size: 1vh;
  color: #664401;
}

.blog-title h1 {
  font-size: 2vh;
  color: #664401;
  text-align: center;
  padding: 15% 0 0 20%;
}

.right-column {
  width: 85%;
  padding: 0 20px;
}

.module {
  background-color: white;
  margin-bottom: 30px;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.module h2 {
  font-size: 2.5vh;
  margin-bottom: 20px;
  color: black;
}

.notes-container {
  display: flex;
  gap: 40px;
}
</style>
