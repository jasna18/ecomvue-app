<template>
  <header class="site-header">
    <div class="container">
      <router-link to="/" class="logo">
        <img src="@/assets/logo.png" alt="E-commerce Logo">
      </router-link>
      <nav class="main-nav">
        <router-link to="/">Home</router-link>
        <router-link to="/products">Products</router-link>
        <router-link to="/contact">Contact</router-link>
      </nav>
      <div class="cart-icon">
        <!-- <span class="cart-count">{{ cartItemCount }}</span> -->
      </div>
    </div>
  </header>
</template>
<script>
</script>
<!-- <script>
export default {
  name: 'SiteHeader',
  props: {
    cartItemCount: {
      type: Number,
      default: 0
    }
  }
}
</script> -->

<style scoped src="@/styles/header.css"></style>
 