<script lang="ts" setup>
import blogData from "~/contentrain/blog/blog.json";

const blog: {
  ID: string;
  createdAt: string;
  updatedAt: string;
  status: string;
  title: string;
  creation: string;
  reading_time: number;
  text: string;
  scheduled: boolean;
  path: string;
}[] = blogData;

console.log(blog);
</script>
<template>
  <div class="app">
    <h1>Testing hehe</h1>
    <div class="blog">
      <div class="blog__posts">
        <div v-for="(post, id) in blog" :key="id" class="blog__post">
          <h2>{{ post.title }}</h2>
          <p>{{ post.text }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f0f0f0;
}

.blog {
  width: 80%;
  max-width: 1200px;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 20px;
}

.blog__posts {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}
</style>
