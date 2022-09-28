<template>
    <h1>¿Quien es este Pokemon?</h1>
    <PokemonPicture v-bind:pokemonId="150" v-bind:showPokemon="true" />
    <PokemonOptions v-bind:pokemons="pokemonArr" />
</template>

<script>
import PokemonOptions from '@/components/PokemonOptions.vue'
import PokemonPicture from '@/components/PokemonPicture.vue'

import getPokemonOptions from '@/helpers/getPokemonOptions'

//console.log(getPokemonOptions())

export default {
    components: { PokemonOptions, PokemonPicture },
    data(){
        return {
            pokemonArr: []
        }
    },
    methods: {
        async mixPokemonArray(){
            this.pokemonArr = await getPokemonOptions()
            //console.log(this.pokemonArr)
        }
    },
    mounted(){
        this.mixPokemonArray()
    }
}
</script>

<style>

</style>