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
<style>
.container{
  background-color: rgb(0, 0, 0);
  border-radius: 10px;
}
.card{
  background-color: black;
  border-radius: 10px;
  /* padding-left: 5px;
  padding-right: 5px; */
  padding:5px
}
.card-body{
  background-color: rgb(255, 255, 255);
}
.card-text{
 color:rgb(0, 0, 0);
}
.card-title{
  color:rgb(0, 0, 0);
}
.h1{

}s
.img{
  border: 5px;
  
  border-color:rgb(68, 175, 194) ;
}

</style>
