<script setup>
import RegisterForm from "../components/forms/RegisterForm.vue"
</script>

<template>
  <h1>Register</h1>
  <register-form />
  <p>Already registered? <router-link to="/login">Login</router-link></p>
</template>
