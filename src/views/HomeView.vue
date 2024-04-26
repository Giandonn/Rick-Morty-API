<script setup>
import { onMounted, reactive, ref } from 'vue';
import ListRick from '../components/ListRick.vue'

let character = reactive(ref())

onMounted (()=>{
  fetch("https://rickandmortyapi.com/api/character/")
  .then(response => response.json())
  .then(response => {
    character.value = response.results
  });
})
</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row">
                <ListRick
                v-for="character in character"
                :key="character.name"
                :name="character.name"
                :image="character.image"
                :gender="character.gender"
                :status="character.status"
                :species="character.species"
                :location="character.location.name"
                :episode="character.episode"
                />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
