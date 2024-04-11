<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="bg-green">{{ msg }}</h1>
    <p>Based on BBC article <a href="https://www.bbc.co.uk/news/science-environment-49349566" class="underline"
        target="_blank" rel="">here</a> </p>
  </div>
</template>
