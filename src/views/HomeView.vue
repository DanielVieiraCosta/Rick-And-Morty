<script setup>
import { onMounted, reactive, ref } from 'vue';
import Personagens from '@/components/Personagens.vue';

let personagens = reactive(ref())

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    personagens.value = response.results
    console.log(personagens)
  })
})
</script>

<template>
  <main style="background-color: #313131;">
    <div class="container">
      <div class="card-body row" style="background-color: black;">
        <p style="color: #CECECE; text-align: center;margin-top: 2rem;"><b style="font-size:xx-large;color: #00FF8B;">Rick and Morty </b>...e o resto</p>
        <Personagens
        v-for="personagem in personagens"
        :key="personagem.name"
        :name="personagem.name"
        :image="personagem.image"
        :status="personagem.status"
        :species="personagem.species"
        :gender="personagem.gender"
        :location="personagem.location.name"
        :episode="personagem.episode"
        />
      </div>
    </div>
    
  </main>
</template>
