<script setup>


</script>

<template>
  <div style="text-align: center;">
    <h1>!זה המקום לשחק וללמוד בכייף כפל</h1>
    <form action="https://???????.com/register" method="POST" style="display: inline-block; text-align: left;">
      <div>
        <label>שם השחקן</label>
        <input type="text" name="username" required />
      </div>
      <div>
        <label>סיסמה</label>
        <input type="password" name="password" required />
      </div>
      <div style="margin-top: 10px;">
        <button type="submit">היכנס למשחק</button>
      </div>
    </form>
    <div style="margin-top: 10px;">
      <router-link to="/login">
        <button type="button">רישום</button>
      </router-link>
    </div>
  </div>
</template>

<style scoped>
form {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
}

input {
  display: block;
  width: 100%;
  padding: 8px;
  margin: 5px 0;
  box-sizing: border-box;
}

button {
  padding: 10px 15px;
  margin: 5px;
  background-color: #28a745;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #218838;
}
</style>
