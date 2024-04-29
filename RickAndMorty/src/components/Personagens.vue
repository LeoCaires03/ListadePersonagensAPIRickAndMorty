<script setup>
    const personagem = defineProps(["name","image", "url","status","species","gender","location","episode"]);
    const totalEp = personagem.episode.length;
   
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3">          
            <img :src="personagem.image" class="card-img-top" alt="...">
            <div class="card-body">
                <p class="card-title">Nome: {{ personagem.name }}</p>
                <p class="card-text">Status: {{ personagem.status }}</p>
                <p class="card-text">Especie: {{ personagem.species }}</p>
                <p class="card-text">Genero: {{ personagem.gender }}</p>
                <p class="card-text">Locazição: {{ personagem.location }}</p>
                <p class="card-text">Quantidade de episodios: {{ totalEp }}</p>
                
            </div>
        </div>
    </div>
</template>

<style>

</style>