<template>
  <div class="home">
    <h1>Welcome to Our E-commerce Store</h1>
    <p>Discover amazing products at great prices!</p>
    <div class="featured-products">
      <h2>Featured Products</h2>
      <div class="product-grid">
        <div class="product-card" v-for="product in featuredProducts" :key="product.id">
          <img :src="product.image" :alt="product.name" class="product-image">
          <h3>{{ product.name }}</h3>
          <p class="price">${{ product.price }}</p>
          <button @click="viewProduct(product.id)">View Details</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      featuredProducts: [
        { id: 1, name: 'Wireless Headphones', price: 99.99, image: 'https://via.placeholder.com/300x200?text=Headphones' },
        { id: 2, name: 'Smart Watch', price: 199.99, image: 'https://via.placeholder.com/300x200?text=Smart+Watch' },
        { id: 3, name: 'Bluetooth Speaker', price: 79.99, image: 'https://via.placeholder.com/300x200?text=Speaker' }
      ]
    }
  },
  methods: {
    viewProduct(id) {
      // Navigate to the product details page
      this.$router.push({ name: 'Products', query: { product: id } });
    }
  }
}
</script>