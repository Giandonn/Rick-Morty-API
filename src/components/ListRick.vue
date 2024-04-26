<script setup>
const character = defineProps(["name", "image", "gender", "status", "species", "location", "episode"]);
const qtdeEp = character.episode.length; 
</script>

<template>
<div class="col-md-4">
    <div class="card mb-3 p-2">
        <div class="card-body">
            <img :src="character.image" alt="">
            <p class="card-title text-center">Name: {{ character.name }}</p>
            <p class="card-title text-center">Gender: {{ character.gender }}</p>
            <p class="card-title text-center">Status: {{ character.status }}</p>
            <p class="card-title text-center">Species: {{ character.species }}</p>
            <p class="card-title text-center">Location: {{ character.location }}</p>
            <p class="card-title text-center">Episodes: {{ qtdeEp }}</p>
        </div>
    </div>
</div>
</template>

<style>
    .card-title {
        margin-top: 10px;
    }

    .card-body {
        font-family:'Times New Roman', Times, serif;
        font-size: 17px;    
    }
</style>