<script setup>
import LoginForm from "../components/forms/LoginForm.vue"
</script>

<template>
  <h1>Login</h1>
  <login-form />
  <p>Need an account?<router-link to="/register">Register here</router-link></p>
</template>
