<script setup>
const pokemon = defineProps(['name', 'xp', 'height', 'image', 'loading'])
</script>

<template>
    <div class="card cardPokemonSelected"
    :class="loading ? '' : 'animate__animated animate__flipInY'">
        <img 
            v-if="pokemon.name"
            :src="pokemon.image"
            height="250"
            class="card-img-top pt-2" 
            :alt="pokemon.name ">
        <img 
            v-else
            src="../assets/Egg.svg"
            height="250"
            class="card-img-top pt-2" 
            alt="???">
        <div class="card-body">
            <h5 class="card-title text-center">{{ pokemon.name || '???'}}</h5>
            <hr>
            <div class="row">
                <section class="col">
                    <strong>XP:</strong>
                    <span class="p-1">{{ pokemon.xp  }}</span>
                </section>
                <section class="col">
                    <strong>Altura:</strong>
                    <span class="p-1">{{ pokemon.height }}</span>
                </section>
            </div>
        </div>
    </div>
</template>

<style scoped>
.cardPokemonSelected {
    height: 75vh;
    background: rgb(72,63,251);
    background: radial-gradient(circle, rgba(230, 52, 52, 0.8) 0%, rgba(252, 173, 70, 0.8) 100%);
}
</style>