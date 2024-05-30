<script setup>
import { ref, provide } from 'vue'

const score = ref(0)

function incrementScore() {
  score.value++
}

provide('score', score)
provide('incrementScore', incrementScore)
</script>

<template>
  <slot></slot>
</template>