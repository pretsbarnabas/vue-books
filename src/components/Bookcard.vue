<script setup lang="ts">
import { type Book } from '../models/BookModel';

defineProps<{ books: Book[] }>()
</script>

<template>
  <div class="book-container">
    <div v-for="book in books" :key="book.title" class="book-card">
      <img :src="book.img_url" :alt="book.title" class="book-card-image">
      <div class="book-card-content">
        <h2 class="book-card-title">{{ book.title }}</h2>
        <p class="book-card-author">{{ book.author }}</p>
        <p class="book-card-description">{{ book.description }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.book-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 20px;
  justify-items: center;
}

.book-card {
  background-color: #fff;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.book-card-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
  transition: opacity 0.3s ease;
}

.book-card-content {
  padding: 16px;
}

.book-card-title {
  font-size: 1.4em;
  font-weight: 600;
  color: #333;
  margin-bottom: 8px;
}

.book-card-author {
  font-size: 1em;
  color: #777;
  margin-bottom: 12px;
}

.book-card-description {
  font-size: 0.95em;
  color: #555;
  line-height: 1.5;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-line-clamp: 3;
  display: -webkit-box;
  -webkit-box-orient: vertical;
}

.book-card:hover .book-card-image {
  opacity: 0.9;
}
</style>
