<template>
    <form @submit.prevent="submitForm">
      <label for="name">Full Name</label>
      <input type="text" id="name" v-model="form.name" required>
  
      <label for="email">Email Address</label>
      <input type="email" id="email" v-model="form.email" required>
  
      <label for="subject">Subject</label>
      <input type="text" id="subject" v-model="form.subject" required>
  
      <label for="message">Message</label>
      <textarea id="message" v-model="form.message" required></textarea>
  
      <button type="submit">Submit</button>
    </form>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          subject: '',
          message: '',
        },
      };
    },
    methods: {
      async submitForm() {
        try {
          await axios.post('/', new URLSearchParams(this.form), {
            headers: {
              'Content-Type': 'application/x-www-form-urlencoded',
            },
          });
          alert('Form submitted successfully!');
          this.resetForm();
        } catch (error) {
          console.error('Error:', error);
          alert('An error occurred. Please try again later.');
        }
      },
      resetForm() {
        this.form = {
          name: '',
          email: '',
          subject: '',
          message: '',
        };
      },
    },
  };
  </script>
  