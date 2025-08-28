<template>
  <div class="about-page">
    <div class="page-header">
      <h1>关于我</h1>
    </div>
    <div class="content">
      <p>这是一个关于页面的示例。您可以在这里介绍自己、您的博客理念或者任何您想分享的内容。</p>
      <p>我是一名热爱技术的开发者，专注于前端开发和用户体验设计。在这个博客中，我将分享我的技术经验、项目实践和行业见解。</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.about-page {
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

.content {
  background-color: white;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.content p {
  font-size: 1.8vh;
  line-height: 1.6;
  margin-bottom: 20px;
  color: #555;
}
</style>
