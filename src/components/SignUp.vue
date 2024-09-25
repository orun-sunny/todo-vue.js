<template>
  <div class="justify-center">
    <h1>Sign up page</h1>
  </div>

  <div class="register">
    <input type="text" placeholder="Enter Name" />
    <input type="text" placeholder="Enter Email" />
    <input type="password" placeholder="Enter Password" />
    <button>Sign Up</button>
  </div>
</template>

<script>
export default {
  name: 'SignUp'
}
</script>

<style scoped>
.register {
  display: flex;
  flex-direction: column;
  gap: 10px; /* Adds space between inputs */
  align-items: center;
}

.register input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  border: 1px solid #ccc; /* Adds a border to the input */
  border-radius: 5px;
  font-size: 16px;
}

button {
  width: 320px;
  height: 45px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
}

button:hover {
  background-color: #45a049; /* Button hover effect */
}
</style>
