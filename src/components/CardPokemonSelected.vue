<script setup>
const pokemon = defineProps(["name", "xp", "height", "img", "loading"]);
</script>

<template>
  <div
    class="card cardPokemon"
    :class="loading ? '' : 'animate__animated animate__flipInY'"
  >
    <img v-if="pokemon.name" :src="img" class="card-img-top pt-2" :alt="name" />
    <img
      v-else
      src="../assets/egg_pokemon.svg"
      class="card-img-top pt-2"
      :alt="name"
    />
    <div class="card-body">
      <h5 class="card-title text-center">{{ pokemon.name || "???" }}</h5>
      <hr />
      <div class="row">
        <section class="col">
          <strong>XP:</strong>
          <span>{{ xp }}</span>
        </section>
        <section class="col">
          <strong>Altura:</strong>
          <span>{{ height }}</span>
        </section>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cardPokemon {
  height: 75vh;
  background: rgb(72, 63, 251);
  background: radial-gradient(
    circle,
    rgba(220, 194, 106, 0.8) 0%,
    rgba(244, 0, 0, 0.8) 100%
  );
}

.cardPokemon img {
  height: 250px;
}

@media (max-width: 768px) {
  .cardPokemon {
    height: 30vh;
    width: 40%;
    margin: 0 auto 10px auto;
  }

  .cardPokemon img {
    height: 100px;
  }
}
</style>
