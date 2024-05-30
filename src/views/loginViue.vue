<script setup>
import { ref } from 'vue';

const username = ref('');
const email = ref('');
const password = ref('');

const handleSubmit = () => {
  console.log('Username:', username.value);
  console.log('Email:', email.value);
  console.log('Password:', password.value);
  // כאן ניתן להוסיף את הלוגיקה של שליחת הנתונים לשרת
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <div>
      <input id="username" v-model="username" type="text" required />
      <label for="username">:שם משתמש</label>
    </div>
    <div>
      <input id="email" v-model="email" type="email" required />
      <label for="email">:כתובת מייל</label>
    </div>
    <div>
      <input id="password" v-model="password" type="password" required />
      <label for="password">:סיסמה</label>
    </div>
  </form>
    <button type="submit">הירשם</button>
</template>

<style>
form {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  margin: auto;
}

div {
  margin-bottom: 1em;
}

label {
  margin-bottom: 0.5em;
  font-weight: bold;
}

input {
  padding: 0.5em;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 0.5em;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
</style>

