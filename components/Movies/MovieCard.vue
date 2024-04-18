<--Movie Card Vue--!>
<template>
    <div class="hover:scale-110 duration-300 text-snow">
      <img :src="`https://image.tmdb.org/t/p/w300/${movie.poster_path}`" class=" h-56 w-auto hover" alt="">
      <h3 class=" line-clamp-2">{{ movie.original_title }}</h3>
      <p>{{ movie.genre }}</p>
      <p>{{ movie.status }}</p>
    </div>
  </template>
  
  <script setup>
  
  defineProps({
    movie: Object
  })
  
  
  </script>
  