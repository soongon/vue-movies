<script setup>
import MovieHeader from './components/MovieHeader.vue';
import MovieFooter from './components/MovieFooter.vue';
import MovieList from './components/MovieList.vue';
import { ref, onMounted } from 'vue';

const movies = ref([]);

onMounted(() => {
    const options = {
        method: 'GET',
        headers: {
            accept: 'application/json',
            Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI5MDM3YTAwN2ZhMmE5MzM1NTdmNWYyMzBlMGYyZTYwZiIsInN1YiI6IjY0OTkzOGVkNmY0M2VjMDBjNWM3MmY4NSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.Rx-ZZRTbVM_ZeG4dP60TI56W8kUOt5v1pAJNwRaoQaY'
        }
    };

    fetch('https://api.themoviedb.org/3/movie/now_playing?language=ko&page=1&region=kr', options)
        .then(response => response.json())
        .then(response => movies.value = response.results)
        .catch(err => console.error(err));
    });

function searchEventHandler(event) {
  const options = {
    method: 'GET',
    headers: {
      accept: 'application/json',
      Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI5MDM3YTAwN2ZhMmE5MzM1NTdmNWYyMzBlMGYyZTYwZiIsInN1YiI6IjY0OTkzOGVkNmY0M2VjMDBjNWM3MmY4NSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.Rx-ZZRTbVM_ZeG4dP60TI56W8kUOt5v1pAJNwRaoQaY'
    }
  };

  fetch('https://api.themoviedb.org/3/search/movie?query='
      + event + '&include_adult=false&language=ko&page=1&region=kr', options)
    .then(response => response.json())
    .then(response => movies.value = response.results)
    .catch(err => console.error(err));
  }
</script>

<template>
  <movie-header @searchTextInput="searchEventHandler"></movie-header>
  <movie-list :movies="movies"></movie-list>
  <movie-footer></movie-footer>
</template>

<style scoped>
</style>
