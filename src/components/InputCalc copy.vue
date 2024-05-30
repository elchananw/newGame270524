<script setup>
import { ref, onMounted } from 'vue'

const props = defineProps({
  singularity: {
    type: Number,
    required: true
  },
  ten: {
    type: Number,
    required: true
  }
})

const userAnswer = ref('')
const inputRef = ref(null)

const checkAnswer = () => {
  const correctAnswer = props.singularity * props.ten
  if (parseInt(userAnswer.value) === correctAnswer) {
    console.log('Correct answer!')
    userAnswer.value = ''
    props.focus()
  } else {
    console.log('Wrong answer, try again.')
  }
}

const focusNextInput = () => {
  if (inputRef.value) {
    inputRef.value.focus()
  }
}

onMounted(() => {
  if (props.focus) {
    props.focus = focusNextInput
  }
})
</script>

<template>
  <div class="greetings">
    <input 
      class="green" 
      ref="inputRef" 
      :placeholder="singularity + '*' + ten" 
      v-model="userAnswer" 
      @input="checkAnswer"
    />
  </div>
</template>





// <script setup>
//קוד gpt לבדיקת תשובה נכונה
// import { ref } from 'vue'

// const props = defineProps({
//   singularity: {
//     type: Number,
//     required: true
//   },
//   ten: {
//     type: Number,
//     required: true
//   }
// })

// const userAnswer = ref('')

// const checkAnswer = () => {
//   const correctAnswer = props.singularity * props.ten
//   if (parseInt(userAnswer.value) === correctAnswer) {
//     alert('Correct answer!')
//   } else {
//     alert('Wrong answer, try again.')
//   }
// }
// </script>

// <template>
//   <div class="greetings">
//     <input class="green" :placeholder="singularity + '*' + ten" v-model="userAnswer" @input="checkAnswer"/>
//   </div>
// </template>



// <script setup>

// קוד נסיוני
// import { ref } from 'vue'
// defineProps({
//   singularity: {
//     type: Number,
//     required: true
//   },
//   ten: {
//     type: Number,
//     required: true
//   }
// })
// // let correctAnswer = singularity;
//     // const singularityRef = ref(singularity)
//     function checkAnswer(e) {
//        console.log(singularityRef);
//     //   console.log(e.data);
//     }
  
// </script>


// <template>
//   <div class="greetings">
//     <input class="green" :placeholder="singularity +'*'+ ten" @input="checkAnswer"/>
//     <!-- <input class="green" :placeholder="singularity +'*'+ ten" @input="checkAnswer" v-model="props.singularity"/> -->
//   </div>
// </template>


