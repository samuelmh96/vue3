<template>
  <div class="post-card">
    <div class="title">Título</div>
    <div class="content">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita
      recusandae ex, nemo dolorum laboriosam, cum alias nam, illo a voluptatibus
      corrupti accusamus ad consequuntur. Beatae at veniam temporibus eum
      quidem.
    </div>
    <PostButton />
  </div>
</template>

<script setup lang="ts">
import PostButton from "./PostButton.vue";
</script>

<style scoped>
.post-card {
  background-color: #f9f9f9;
  width: 300px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  padding: 20px;
  margin: 20px;
}

.post-card .title {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
}

.post-card .content {
  font-size: 16px;
  color: #666;
  margin-bottom: 20px;
}
</style>
