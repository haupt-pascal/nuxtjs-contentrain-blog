<script lang="ts" setup>
import { ref, onMounted } from 'vue';
import { useRoute } from 'vue-router';
import blogData from "~/contentrain/blog/blog.json";

const route = useRoute();

interface BlogPost {
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
}

const blog: BlogPost[] = blogData;

const slug = route.params.slug as string;
const post = ref<BlogPost | undefined>(undefined);

onMounted(() => {
  post.value = blog.find(p => p.ID === slug);
  if (post.value) {
    console.log('Post found:', post.value);
  } else {
    console.log('No post found for slug:', slug);
  }
});
</script>

<template>
  <div class="app">
    <Navigation />
    <div class="blog">
      <div class="blog__posts">
        <div v-if="post" class="blog__post">
          <h2>{{ post.title }}</h2>
          <MDC :value="post.text" class="markdown" />
        </div>
        <div v-else class="blog__post">
          <h2>Post not found</h2>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
body {
  background: #1D1E20;
}

.app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.blog {
  width: 80%;
  max-width: 1200px;
  border-radius: 10px;
  padding: 20px;
  height: 100%;
}

.blog__posts {
  display: grid;
  gap: 20px;
  height: 100%;
}

.line {
  background: #2E2F33 !important;
  padding: 12px;
}

pre {
  border-radius: 20px !important;
}

</style>