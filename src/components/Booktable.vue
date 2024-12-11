<script setup lang="ts">
import { type Book } from '../models/BookModel'

defineProps<{ books: Book[] }>()
</script>

<template>
  <table class="book-table">
    <thead>
      <tr>
        <th>Author</th>
        <th>Title</th>
        <th>Description</th>
        <th>Image</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="book in books" :key="book.title">
        <td>{{ book.author }}</td>
        <td>{{ book.title }}</td>
        <td>{{ book.description }}</td>
        <td>
          <img :src="book.img_url" :alt="book.title" class="book-image">
        </td>
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
  .book-table {
    width: 100%;
    border-collapse: collapse;
    margin: 30px 0;
    font-size: 16px;
    color: #333;
    background-color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
  }

  .book-table th,
  .book-table td {
    padding: 12px;
    text-align: left;
    border-bottom: 1px solid #ddd;
  }

  .book-table th {
    background-color: #6c63ff;
    color: white;
    font-weight: 600;
    font-size: 14px;
  }

  .book-table td {
    background-color: #f9f9f9;
    font-size: 14px;
    line-height: 1.6;
  }

  .book-table tr:nth-child(even) td {
    background-color: #f1f1f1;
  }

  .book-table tr:hover td {
    background-color: #f0f4ff;
    cursor: pointer;
  }

  .book-image {
    width: 80px;
    height: auto;
    object-fit: cover;
    border-radius: 4px;
    transition: transform 0.3s ease;
  }
</style>
