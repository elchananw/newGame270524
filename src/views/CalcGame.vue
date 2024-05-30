<script setup>
import { ref, reactive, nextTick, onMounted } from 'vue'
import InputCalc from '../components/InputCalc.vue'

const answersCount = ref(0)




const focusNext = (currentInput) => {
  const inputs = Array.from(document.querySelectorAll('input.myInput'))
  const currentIndex = inputs.indexOf(currentInput)
 
  if (currentIndex >= 0 && currentIndex < inputs.length - 1) {
    nextTick(() => {
      inputs[currentIndex + 1].focus()
      inputs[currentIndex].style.display = 'none'
      console.log(currentIndex) 
    })
  }
}




const incrementCorrectAnswers = () => {
  answersCount.value += 1
  if (answersCount.value === 100) {
    resetGame()
  }
}
</script>

<template>
  <div class="container" >
    <div class="column" v-for="column in 10" :key="column">
      <div v-for="row in 10" :key="row">
        <InputCalc :singularity="column" :ten="row" :focus="focusNext" @correct="incrementCorrectAnswers" />
      </div>
    </div>
  </div>
</template>

<style>
.container {
  display: flex;
  flex-direction: row;
      background-image: url(../assets/sea.jpg);
      width: 500px;
      height: 265px;
    }
.column {
  width: 50px;
  display: flex;
  flex-direction: column;
}
.myInput {
  padding: 0;
  margin: 0;
  height: 26px;
  width: 50px;
  display: flex;
  justify-content: center;
}
</style>

