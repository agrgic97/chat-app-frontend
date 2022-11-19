<script setup>
import { Form, Field, ErrorMessage } from "vee-validate"
import * as Yup from "yup"

const loginSchema = Yup.object({
  username: Yup.string().required("Enter your username"),
  password: Yup.string().min(6).required("Enter your password"),
})

const submitForm = () => {}
</script>

<template>
  <Form @submit="submitForm" :validation-schema="loginSchema">
    <Field name="username" type="text" placeholder="Username" />
    <ErrorMessage name="username" />
    <br />
    <Field name="password" type="password" placeholder="Password" />
    <ErrorMessage name="password" />
    <br />
    <button type="submit">Login</button>
  </Form>
</template>
