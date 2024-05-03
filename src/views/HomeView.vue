<script setup>
  import { onMounted, reactive, ref} from 'vue';
  import ListCharacters from '../components/ListCharacters.vue';

  let character = reactive(ref());
  
  onMounted(() => {
    fetch("https://rickandmortyapi.com/api/character")
    .then(response => response.json())
    .then(response => {
      character.value = response.results
      console.log(character.value)
    })
  })

</script>

<template>
  <main class="container">
    <div class="row">
      <div v-for="(character, index) in character" :key="index" class="col-md-4 mb-3">
        <div class="card">
          <img :src="character.image" class="card-img-top" alt="...">
          <div class="card-body">
            <h2 class="card-title">{{ character.name }}</h2>
            <h4>Status: {{ character.status }}</h4>
            <h4>Espécie: {{ character.species }}</h4>
            <h4>Gênero: {{ character.gender }}</h4>
            <h4>Localização: {{ character.location.name }}</h4>
            <h4>Número de episódios: {{ character.episode.length }}</h4>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
