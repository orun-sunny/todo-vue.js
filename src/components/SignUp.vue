<template>
  <div class="justify-center">
    <h1>Sign up page</h1>
  </div>

  <div class="register">
    <input type="text " v-model="name" placeholder="Enter Name" />
    <input type="text" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Password" />
    <button v-on:click="signUp">Sign Up</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'SignUp',
  data() {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    async signUp() {
      console.warn('signUp')
      let result = await axios.post('http://localhost:3000/users', {
        email: this.email,
        name: this.name,
        password: this.password
      })
      console.warn(result)
      if (result.status == 201) {
        alert('Sign up Done')
      }
      localStorage.setItem('user-info', JSON.stringify(result.data))
    }
  }
}
</script>

<style scoped>
.register {
  display: flex;
  flex-direction: column;
  gap: 12px; /* Adds space between inputs */
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
