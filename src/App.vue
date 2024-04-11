<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TravelSelect from './components/TravelSelect.vue'
</script>

<template>
  <header class="px-5 py-6 flex items-center justify-center shadow-md">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="55" height="55" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>
  <main class="container mx-auto px-5 my-3">
    <TravelSelect />

  </main>

</template>
