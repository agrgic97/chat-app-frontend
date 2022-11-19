<script setup>
import { Form, Field, ErrorMessage } from "vee-validate"
import * as Yup from "yup"

const registrationSchema = Yup.object({
  username: Yup.string().required("Username is required"),
  email: Yup.string().email().required("E-Mail is required"),
  password: Yup.string().min(6).required("Password is required"),
  passwordConfirmation: Yup.string()
    .oneOf([Yup.ref("password"), null], "Passwords must match")
    .required("Confirm your password"),
})

const submitForm = () => {}
</script>

<template>
  <Form @submit="submitForm" :validation-schema="registrationSchema">
    <Field name="username" type="text" placeholder="Username" />
    <ErrorMessage name="username" />
    <br />
    <Field name="email" type="email" placeholder="Email" />
    <ErrorMessage name="email" />
    <br />
    <Field name="password" type="password" placeholder="Password" />
    <ErrorMessage name="password" />
    <br />
    <Field
      name="passwordConfirmation"
      type="password"
      placeholder="Confirm Password"
    />
    <ErrorMessage name="passwordConfirmation" />
    <br />
    <button type="submit">Create an account</button>
  </Form>
</template>
