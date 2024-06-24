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
</script>
<template>
  <div class="app">
    <div class="about">
      <h1>Hey, I'm Pascal 👋</h1>
      <p>
        I am working at group.one as a linux system administrator. I am also a
        software engineer with a huge focus on frontend development and devops.
      </p>
    </div>
    <div class="blog">
      <div class="blog__posts">
        <div v-for="(post, id) in blog" :key="id" class="blog__post">
          <h2>{{ post.title }}</h2>
          <MDC :value="post.text" class="markdown" />
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
}

.blog {
  width: 80%;
  max-width: 1200px;
  border-radius: 10px;
  padding: 20px;
}

.blog__posts {
  display: grid;
  gap: 20px;
}

.line {
  background: #2E2F33 !important;
  padding: 12px;
}

pre {
  border-radius: 20px !important;
}

</style>

<!--
<style>
pre {
  padding: 1em 0 !important;
  --tw-prose-pre-bg: #8881 !important;
}
.line {
  display: block;
  padding: 0 1rem;
  background: red !important;
}
.line.highlight {
  width: 100%;
  background-color: #8881 !important;
}
.line.diff.remove {
  background-color: rgba(194, 58, 58, 0.3) !important;
}
.line.diff.add {
  background-color: rgba(46, 141, 46, 0.3) !important;
}
.line.diff.remove::before {
  content: '-';
  color: #c23a3a;
  position: absolute;
}
.line.diff.add::before {
  content: '+';
  color: #23b73c;
  position: absolute;
}
</style>
-->