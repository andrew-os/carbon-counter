<script setup lang="ts">
import { ref, computed, } from 'vue';
import TotalEmissions from './TotalEmissions.vue'

const distance = ref('')
// const checkedNames = ref([])

const transports = [
  { id: 1, name: 'Plane', coGPerKm: '133', selected: true },
  { id: 2, name: 'Car', coGPerKm: '171', selected: false },
  { id: 3, name: 'Bus', coGPerKm: '104', selected: false },
  { id: 4, name: 'Coach', coGPerKm: '27', selected: false },
]

const selectedTransport = computed(() => {
  return transports.filter(transport => transport.selected)
})
</script>

<template>
  <div class="my-6">
    <h2 class="text-xl uppercase font-bold opacity-85">Transport method</h2>
    <ul class="flex gap-x-2 py-4 flex-row">
      <li v-for="transport in transports" :key="transport.id">
        <label>
          {{ transport.name }}
          <input type="checkbox" v-model="transport.selected" />
        </label>
        <p><span>{{ transport.coGPerKm }} </span> <br /></p>
      </li>

    </ul>
    <p>emissions per passenger per km travelled</p>
  </div>
  <section v-show="selectedTransport">
    <p>You are travelling by
      <span v-for="transport in selectedTransport" :key="transport.id">
        {{ transport.name }}
      </span>
    </p>
  </section>
  <div class="my-6">
    <h2 class="text-xl uppercase font-bold opacity-85">Distance travelled</h2>
    <p class="my-3"><input type="text" v-model="distance" class="border-teal-900 border-2 rounded py-1 px-2"
        placeholder="Distance in Km's" /></p>
    <h3>{{ distance }}</h3>
  </div>

  <TotalEmissions />
</template>