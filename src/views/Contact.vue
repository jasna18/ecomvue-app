<template>
  <div class="contact">
    <h1>Contact Us</h1>
    <div class="contact-info">
      <p>Email: info@ecommercestore.com</p>
      <p>Phone: (123) 456-7890</p>
      <p>Address: 123 Store Street, City, Country</p>
    </div>
    
    <form class="contact-form" @submit.prevent="submitForm">
      <div class="form-group">
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="form.name" required>
      </div>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="form.email" required>
      </div>
      <div class="form-group">
        <label for="subject">Subject:</label>
        <input type="text" id="subject" v-model="form.subject" required>
      </div>
      <div class="form-group">
        <label for="message">Message:</label>
        <textarea id="message" v-model="form.message" rows="5" required></textarea>
      </div>
      <button type="submit">Send Message</button>
    </form>
    
    <div v-if="submitted" class="thank-you-message">
      <h3>Thank you for your message!</h3>
      <p>We'll get back to you soon.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      },
      submitted: false
    }
  },
  methods: {
    submitForm() {
      // In a real app, you would send this to a backend
      console.log('Form submitted:', this.form);
      this.submitted = true;
      this.form = { name: '', email: '', subject: '', message: '' };
      
      // Reset form after 5 seconds
      setTimeout(() => {
        this.submitted = false;
      }, 5000);
    }
  }
}
</script>

<style scoped>
.contact-info {
  margin-bottom: 30px;
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 5px;
}

.thank-you-message {
  margin-top: 20px;
  padding: 20px;
  background-color: #d4edda;
  color: #155724;
  border-radius: 5px;
}
</style>