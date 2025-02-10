<template>
  <div class="BreadCard">
    <img src="bread.image" alt="bread.name" class="weapon-image" />
    <h3>{{ bread.name }}</h3>
  </div>
  <div class="MeatCard">
    <img src="meat.image" alt="meat.name" class="meat-image" />
    <h3>{{ meat.name }}</h3>
  </div>
  <div class="CheeseCard">
    <img src="cheese.image" alt="cheese.name" class="cheese-image" />
    <h3>{{ cheese.name }}</h3>
  </div>
  <div class="CondimentCard">
    <img src="condiment.image" alt="condiment.name" class="condiment-image" />
    <h3>{{ condiment.name }}</h3>
  </div>
  <div class="VegetableCard">
    <img src="vegetable.image" alt="vegetable.name" class="vegetable-image" />
    <h3>{{ vegetable.name }}</h3>
  </div>
</template>

<script setup>
import bread from './ToppingsList.vue'
import meat from './ToppingsList.vue'
import cheese from './ToppingsList.vue'
import condiment from './ToppingsList.vue'
import vegetable from './ToppingsList.vue'
defineProps({
  bread: Object,
  meat: Object,
  cheese: Object,
  condiment: Object,
  vegetable: Object,
})
</script>
<style scoped>
.bread-card {
  font-size: 20px;
  background-color: antiquewhite;
}
</style>
