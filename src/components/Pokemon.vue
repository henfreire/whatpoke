<script setup>
import Icon from "@/components/icons/Icon.vue";
defineProps({
  data: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div class="card">
    <div class="avatar">
      <img
        class="pokemon-image"
        :src="`https://assets.pokemon.com/assets/cms2/img/pokedex/detail/${String(
          data.pokedex_number
        ).padStart(3, '0')}.png`"
      />
      <span class="name">{{ data.name }}</span>
    </div>
    <div class="infos">
      <div class="item generation">
        <span class="value">{{ data.generation }}</span>
        <span class="label">GEN</span>
      </div>
      <div class="item type">
        <icon :name="data.type1" />
        <span>{{ data.type1 }}</span>
      </div>
      <div class="item type">
        <icon :name="data.type2 || data.type1" />
        <span>{{ data.type2 || data.type1 }}</span>
      </div>
      <div class="item height">
        <span class="value">{{ data.height_m }}</span>
        <span class="label">M</span>
      </div>
      <div class="item wheight">
        <span class="value">
          {{ data.weight_kg }}
        </span>
        <span class="label">KG</span>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.card {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  background-color: #232323;
  border-radius: 10px;
  padding: 1rem;
  margin: 1rem;
  transition: all 0.3s ease;
  color: var(--vt-c-white);
}
.pokemon-image {
  max-width: 100px;
}
.infos {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  .item {
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    align-items: center;
    margin: 5px;
    justify-content: center;
    width: 50px;
    height: 50px;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    border-radius: 50%;
    text-align: center;
    color: var(--vt-c-white);
    border: 1px solid var(--vt-c-white);
    position: relative;
  }
}
.avatar {
  display: flex;
  flex-flow: column;
  align-items: center;
}
.type {
  svg {
    width: 25px;
    height: 25px;
  }
  span {
    font-size: 8px;
  }
}
.generation {
  .value {
    font-size: 20px;
  }
  .label {
    font-size: 8px;
  }
}
.wheight,
.height {
  line-height: 1;
  .value {
    font-size: 18px;
    margin-bottom: 2px;
  }
  .label {
    font-size: 14px;
  }
}
</style>