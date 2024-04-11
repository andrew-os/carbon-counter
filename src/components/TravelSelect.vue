<script setup lang="ts">
import { ref } from 'vue';
import TotalEmissions from './TotalEmissions.vue'

const distance = ref('')
const checkedNames = ref([])
</script>

<template>
  <div class="my-6">
    <h2 class="text-xl uppercase font-bold opacity-85">Transport method</h2>
    <div class="flex gap-x-2 py-4 flex-row">
      <div>
        <input type="checkbox" id="plane" value="Plane" v-model="checkedNames">
        <label for="plane">Plane</label>
      </div>

      <div>
        <input type="checkbox" id="car" value="Car" v-model="checkedNames">
        <label for="car">Car</label>
      </div>
      <div>
        <input type="checkbox" id="bus" value="Bus" v-model="checkedNames">
        <label for="bus">Bus</label>
      </div>
      <div>
        <input type="checkbox" id="rail" value="Rail" v-model="checkedNames">
        <label for="rail">Rail</label>
      </div>
    </div>

  </div>
  <div class="my-6">
    <h2 class="text-xl uppercase font-bold opacity-85">Distance travelled</h2>
    <p class="my-3"><input type="text" v-model="distance" class="border-teal-900 border-2 rounded py-1 px-2"
        placeholder="Distance in Km's" /></p>
    <h3>{{ distance }}</h3>
  </div>

  <TotalEmissions />
</template>