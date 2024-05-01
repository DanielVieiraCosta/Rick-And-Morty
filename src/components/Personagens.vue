<script setup>
  const personagem = defineProps(["name", "image", "status", "species", "gender", "location", "episode"])
</script>

<template>
    <div class="col-md-6 col-sm-12">
      <div class="card-body row" style="margin: 1rem; background-color: #13182F; color: #CECECE;">
        <div class="img-personagem col-xxl-6 col-sm-12" style="padding-left: 0;">
          <img :src="personagem.image" style="width: 19rem;" class="card-img-top" alt="...">
        </div>
        <div class="info col-xxl-5 col-sm-12" style="margin-top: 1rem;">
          <p><b>{{ personagem.name }}</b></p>
          <p>Status: {{ personagem.status }}</p>
          <p>Espécie: {{ personagem.species }}</p>
          <p>Gênero: {{ personagem.gender }}</p>
          <p>Localização atual: {{ personagem.location }}</p>
          <p>Participou de {{ personagem.episode.length }} episódeos</p>
        </div>
      </div>
    </div>
</template>

<style>
</style>
