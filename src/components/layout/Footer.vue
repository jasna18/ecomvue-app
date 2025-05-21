<template>
  <footer class="site-footer">
    <div class="container">
      <div class="footer-section">
        <h3>Quick Links</h3>
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/products">Products</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </div>
      <div class="footer-section">
        <h3>Contact Info footer</h3>
        <p>Email: info@ecommerce.com</p>
        <p>Phone: (123) 456-7890</p>
      </div>
      <div class="copyright">
        &copy; {{ currentYear }} E-commerce Store. All rights reserved.
      </div>
    </div>
  </footer>
</template>
<script>
</script>
<!-- 
<script>
export default {
  name: 'SiteFooter',
  computed: {
    currentYear() {
      return new Date().getFullYear()
    }
  }
}
</script>
 -->
<style scoped src="@/styles/footer.css"></style> 