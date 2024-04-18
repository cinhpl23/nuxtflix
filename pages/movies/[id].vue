<template>
  <div class="flex">
    <div class="">
      <h1 class="text-snow">{{ movie.title }}</h1>
    </div>
    <img width="1220" height="659" :src="`https://image.tmdb.org/t/p/original${movie.backdrop_path}`"
      :alt="movie.title" class="h-full object-cover w-2/3" />
  </div>
    <p class="text-snow">{{ movie.overview }}</p>
  <div v-if="movie?.videos?.results" class="text-snow">
    <div v-for="video in movie.videos.results" :key="video.id">
      <iframe width="560" height="315" :src="`https://www.youtube.com/embed/${video.key}`" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
  </div>
</template>

<script setup>
const { params, query } = useRoute()
const { getMovieById } = useTmdb()

const movie = ref({})

onMounted(async () => {
  movie.value = await getMovieById(params.id,'videos')
})


</script>