<template>
    <q-page padding>
      <div class="q-pa-md">
        <h1>Contact Us</h1>
        <p>
          We are always ready to help you. If you have any questions, suggestions or complaints, please do not hesitate to contact us via the form below or the contact information provided.
        </p>
        
        <q-form @submit.prevent="submitForm">
          <q-input v-model="name" label="Nama" outlined required />
          <q-input v-model="email" label="Email" type="email" outlined required />
          <q-input v-model="message" label="Pesan" type="textarea" outlined required />
          
          <q-btn type="submit" label="Send" color="primary" class="q-mt-md" />
        </q-form>
        
        <div class="q-mt-lg">
          <h2>Informasi Kontak</h2>
          <p><strong>Alamat:</strong> Jl. Melati</p>
          <p><strong>Telepon:</strong> (+62) 8423562356</p>
          <p><strong>Email:</strong> beautybar@gmail.com</p>
          
        </div>
      </div>
    </q-page>
  </template>
  
  <script>
  import { ref } from 'vue'
  
  export default {
    setup () {
      const name = ref('')
      const email = ref('')
      const message = ref('')
  
      const submitForm = () => {
        // Proses pengiriman formulir
        console.log('Formulir dikirim:', { name: name.value, email: email.value, message: message.value })
        alert('Pesan Anda telah terkirim. Terima kasih!')
        
        // Reset form
        name.value = ''
        email.value = ''
        message.value = ''
      }
  
      return {
        name,
        email,
        message,
        submitForm
      }
    }
  }
  </script>
  
  <style>
  .q-page {
    max-width: 600px;
    margin: 0 auto;
  }
  
  h1, h2 {
    color: #e4419b;
  }
  
  p {
    color: #df86b2;
  }
  </style>
  