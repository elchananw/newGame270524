<script setup>
import { ref, onMounted, inject } from 'vue'

const props = defineProps({
  singularity: {
    type: Number,
    required: true
  },
  ten: {
    type: Number,
    required: true
  },
  focus: {
    type: Function
  }
})

const userAnswer = ref('')
const inputRef = ref(null)
const incrementScore = inject('incrementScore') 

const checkAnswer = () => {
  const correctAnswer = props.singularity * props.ten
  if (parseInt(userAnswer.value) === correctAnswer) {
    console.log('Correct answer!')
    incrementScore() 
    props.focus(inputRef.value) 
  } else {
    console.log('Wrong answer, try again.')
  }
}

onMounted(() => {
  inputRef.value.focus()
})
</script>

<template>
  <div class="greetings">
    <input
      ref="inputRef"
      class="myInput"
      :placeholder="singularity + '*' + ten"
      v-model="userAnswer"
      @input="checkAnswer"
    />
  </div>
</template>