<script setup>
// props - onMounted, reactive, ref
import { onMounted, reactive, ref} from 'vue';
import Personagens from '../components/Personagens.vue';
let personagens = reactive(ref())


// fetch - axios 
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
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col">
          <div class="card">
            <div class="card-body row">
              <Personagens
            v-for="perso in personagens"  
            :key="perso.name" 
            :name="perso.name" 
            :image="perso.image" 
            :url="perso.url"
            :status="perso.status"
            :species="perso.species"
            :gender="perso.gender"
            :location="perso.location.name"
            :episode="perso.episode"
            />
            </div>
          </div>
        </div>
      </div>
    </div>
  </main> 
</template>
