<script setup>
const pokemon = defineProps(["name", "xp", "height", "img", "loading"]);
</script>

<template>
  <div
    class="card cardPokemon"
    :class="loading ? '' : 'animate__animated animate__flipInY'"
  >
    <img
      v-if="pokemon.name"
      :src="img"
      class="card-img-top pt-2"
      :alt="name"
      height="250"
    />
    <img
      v-else
      src="../assets/egg_pokemon.svg"
      class="card-img-top pt-2"
      :alt="name"
      height="250"
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
</style>
