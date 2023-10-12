<script setup>
defineProps(['movie']);
</script>

<template>
    
<div class="m-3 max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
    <a href="#">
        <img class="rounded-t-lg" src="https://dnm.nflximg.net/api/v6/2DuQlx0fM4wd1nzqm5BFBi6ILa8/AAAAQcB9qDJIQQk9Omm_Vo7XZnOXOYSTe_fGItBbRNTkBKQnIbFWaDDxbI-rTdLdQbA8VB5xZ6clMnEN4_7xIqV4ZLMUvJxECKxwqUXYuTFcVnGgn_9GJQz5bIC4s-YHQ2CKMSGQbE20Ei3hp37HXMBrWJjx.jpg?r=c47" alt="" />
    </a>
    <div class="p-5">
        <a href="#">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
                {{ movie.title }}</h5>
        </a>
        <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
            {{ movie.overview }}</p>
        
    </div>
</div>

</template>

<style>
</style>