<template>
  <component :is="components[name]"/>
</template>

<script setup>
import bug from "./types/bug.vue"
import dark from "./types/dark.vue"
import dragon from "./types/dragon.vue"
import electric from "./types/electric.vue"
import fairy from "./types/fairy.vue"
import fighting from "./types/fighting.vue"
import fire from "./types/fire.vue"
import flying from "./types/flying.vue"
import ghost from "./types/ghost.vue"
import grass from "./types/grass.vue"
import ground from "./types/ground.vue"
import ice from "./types/ice.vue"
import normal from "./types/normal.vue"
import poison from "./types/poison.vue"
import psychic from "./types/psychic.vue"
import rock from "./types/rock.vue"
import steel from "./types/steel.vue"
import water from "./types/water.vue"

const components = {
  bug,
  dark,
  dragon,
  electric,
  fairy,
  fighting,
  fire,
  flying,
  ghost,
  grass,
  ground,
  ice,
  normal,
  poison,
  psychic,
  rock,
  steel,
  water,
}
defineProps({
  name: {
    type: String,
    required: true,
  },
});
</script>