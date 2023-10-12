<script setup>
import MovieCard from './MovieCard.vue';

defineProps(['movies']);
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
