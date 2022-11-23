<script setup>
import pokeData from "@/data.json";
import Pokemon from "@/components/Pokemon.vue";
import { ref, computed } from "vue";

const data = pokeData;
const search = ref();

const getPokemonList = computed(() => {
  const searchName = search.value?.toLowerCase()

  return data
    .filter((pokemon) => {
      return !searchName || pokemon.name.toLowerCase().includes(searchName);
    })
    .splice(0, 6);
});
</script>

<template>
  <main>
    <h1>Pokedex</h1>
    <input class="search" type="text" placeholder="Search your pokemon here..." v-model="search"  />
    <div v-if="getPokemonList.length" class="pokemon-list">
      <pokemon
        v-for="pokemon in getPokemonList"
        :key="pokemon.pokedex_number"
        :data="pokemon"
      />
    </div>
  </main>
</template>
<style scoped lang="scss">
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 40px;
}
.pokemon-list {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
.search {
  width: 100%;
  height: 40px;
  border-radius: 10px;
  border: none;
  padding: 0 10px;
  margin-bottom: 20px;
  background: transparent;
  font-size: 20px;
  color: #fff;

  &:focus{
    border: 1px solid #fff;
    outline: none;
  }
}
</style>