<script setup>
import { ref, computed } from 'vue';
const pokemon = defineProps(['name', 'xp', 'height', 'image', 'loading', 'abilities'])
const showAbilities = ref(false);

const formattedHeight = computed(() => {
    if (!pokemon.height) return '0';
    return (pokemon.height / 10);
});

</script>

<template>
    <div class="card cardPokemonSelected" :class="loading ? '' : 'animate__animated animate__flipInY'">
        <img v-if="pokemon.name" :src="pokemon.image" class="card-img-top pt-2" :alt="pokemon.name">
        <img v-else src="../assets/Egg.svg" class="card-img-top pt-2 opacity-50" alt="???">
        
        <div class="card-body">
            <h5 class="card-title text-center text-uppercase fw-bold">{{ pokemon.name || '???' }}</h5>
            <hr>

            <div class="row justify-content-center g-3">
                <section class="col-6 col-md-4"> 
                    <div class="p-2 border rounded bg-light-opacity status-box">
                        <strong class="d-block small text-uppercase">XP</strong>
                        <span>{{ pokemon.xp || 0 }}</span>
                    </div>
                </section>
                <section class="col-6 col-md-4">
                    <div class="p-2 border rounded bg-light-opacity status-box">
                        <strong class="d-block small text-uppercase">Altura</strong>
                        <span>{{ formattedHeight }}m</span>
                    </div>
                </section>
            </div>

            <div class="mt-4">
                <button 
                    class="btn btn-sm btn-dark w-100 d-md-none mb-2" 
                    @click="showAbilities = !showAbilities"
                    v-if="pokemon.name">
                    {{ showAbilities ? 'Ocultar Habilidades' : 'Ver Habilidades' }}
                </button>

                <div :class="{'d-none d-md-block': !showAbilities, 'd-block': showAbilities}">
                    <p class="text-center fw-bold mb-2 small text-uppercase text-dark-emphasis">Habilidades</p>
                    <div class="d-flex flex-wrap justify-content-center gap-2">
                        <div v-for="(item, index) in pokemon.abilities" :key="index" class="ability-badge">
                            {{ item.ability.name }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.cardPokemonSelected {
    height: 75vh;
    background: radial-gradient(circle, rgba(230, 52, 52, 0.8) 0%, rgba(252, 173, 70, 0.8) 100%);
    color: white;
    border: none;
}

.cardPokemonSelected img {
    height: 250px;
    object-fit: contain;
}

.status-box {
    max-width: 120px;
    margin: 0 auto;
}

.text-dark-emphasis {
    color: #212529 !important; /* Texto das habilidades bem escuro */
}

.bg-light-opacity {
    background: rgba(255, 255, 255, 0.15);
    border: 1px solid rgba(255, 255, 255, 0.3) !important;
}

.ability-badge {
    background: rgba(0, 0, 0, 0.1); /* Badge levemente escurecida */
    border: 1px solid rgba(0, 0, 0, 0.2);
    color: #212529; /* Texto interno da habilidade escuro */
    border-radius: 8px;
    padding: 5px 12px;
    font-size: 0.85rem;
    font-weight: 500;
    text-transform: capitalize;
}

@media (max-width: 768px) {
    .cardPokemonSelected {
        height: auto;
        width: 100%;
        margin-bottom: 20px;
    }
    .cardPokemonSelected img {
        height: 150px;
    }
}
</style>