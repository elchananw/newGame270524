<template>
  <div class="score-counter">
    ניקוד: {{ score }}
  </div>
</template>

<script setup>
import { inject } from 'vue'

const score = inject('score')
</script>

<style scoped>
.score-counter {
  font-size: 1.5rem;
  margin: 1rem;
  text-align: center;
}
</style>