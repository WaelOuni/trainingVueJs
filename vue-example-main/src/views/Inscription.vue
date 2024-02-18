<!-- Inscription.vue -->

<template>
    <div class="inscription-container">
      <h1>Inscription Customer Form</h1>
      
      <form @submit.prevent="submitForm" class="inscription-form">
          <div class="form-group">
              <label for="name">FirstName:</label>
              <input type="text" id="firstName" v-model="formData.firstName" required>
          </div>
          <div class="form-group">
              <label for="name">LastName:</label>
              <input type="text" id="lastName" v-model="formData.lastName" required>
          </div>
          
          <!-- <div class="form-group">
              <label for="email">Email:</label>
              <input type="email" id="email" v-model="formData.email" required>
          </div> -->
          
          <button type="submit">Submit</button>
      </form>
      <!-- TODO connect backend -->
      <div v-if="submitted" class="success-message">
          <p>Thank you for your inscription, {{ formData.firstName }}!</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          firstName: '',
          lastName: '',
        },
        submitted: false,
      };
    },
    methods: {
      submitForm() {
        // Perform form submission logic here (e.g., send data to server)
        // For simplicity, let's just toggle a submitted flag in this example
        this.submitted = true;
      },
    },
  };
  </script>
  
  <style scoped>
  .inscription-container {
    max-width: 400px;
    margin: 0 auto;
    text-align: center;
  }
  
  .inscription-form {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input {
    padding: 8px;
    width: 100%;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin-top: 3px;
  }
  
  button {
    background-color: #4caf50;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #45a049;
  }
  
  .success-message {
    margin-top: 20px;
    background-color: #dff0d8;
    padding: 15px;
    border: 1px solid #d6e9c6;
    border-radius: 4px;
    color: #3c763d;
  }
  </style>
  