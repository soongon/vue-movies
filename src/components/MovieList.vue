<script setup>
import { onMounted, ref } from 'vue';
import MovieCard from './MovieCard.vue';

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
</script>

<template>
    <section class="max-w-7xl mx-auto py-7">
        <div class="flex justify-start flex-wrap">
            <movie-card 
                v-for="movie in movies" 
                :key="movie.id"
                :movie="movie"
            />
        </div>
    </section>
</template>

<style>
</style>