<template>
  <div class="options-container">
    <ul>
        <li v-for="pokemon in pokemons" v-bind:key="pokemon.id" @click="$emit('selectionPokemon', pokemon.id)">
            {{ pokemon.name }}
        </li>
    </ul>
  </div>
</template>

<script>
export default {
    props: {
        pokemons: {
            type: Array,
            required: true
        }
    }
};
</script>

<style scope>
/* Pokemon Options */
ul {
  list-style-type: none;
  padding: 0;

}
li {
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  cursor: pointer;
  margin-bottom: 10px;
  width: 250px;
  max-width: 250px; /* Ancho máximo para pantallas grandes */
}

li:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.options-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap; /* Permite que los elementos se ajusten en filas según el ancho */
}

@media (max-width: 600px) {
  li {
    margin-bottom: 5px;
    font-size: 14px; /* Tamaño de texto más pequeño para pantallas pequeñas */
  }
}
</style>