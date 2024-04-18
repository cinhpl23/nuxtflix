<template>

  <h1 class="text-5xl text-snow text-center uppercase font-bold my-4 mb-8">Movies</h1>
  <hr>
  <div class="space-x-0 flex justify-center border-black">
    <button v-for="{ params, label } in menu" :key="params" @click="refineMovies(params)"
      class="bg-primary text-snow px-8 uppercase py-2 first:rounded-l-md last:rounded-r-md">{{ label
      }}</button>
  </div>
  <Carousel class="mt-8">
    <MoviesCard :movie="movie" v-for="movie in movies" />
  </Carousel>
</template>
<script setup>

const { getMovies } = useTmdb()
const movies = ref([]);

const menu = [
  { params: "upcoming", label: 'Bientot' },
  { params: "popular", label: 'Populaire' },
  { params: "top_rated", label: 'Top' },
  { params: "now_playing", label: "A l'affiche" }
]

async function refineMovies(params) {
  movies.value = await getMovies(params)
}

onMounted(() => {
  refineMovies("upcoming")
})

</script>