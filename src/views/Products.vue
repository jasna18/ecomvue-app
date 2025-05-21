<template>
  <div class="products">
    <h1>Our Products</h1>
    <div class="product-filters">
      <input type="text" v-model="searchQuery" placeholder="Search products...">
      <select v-model="selectedCategory">
        <option value="">All Categories</option>
        <option v-for="category in categories" :key="category">{{ category }}</option>
      </select>
    </div>
    <div class="product-grid">
      <div class="product-card" v-for="product in filteredProducts" :key="product.id">
        <img :src="product.image" :alt="product.name" class="product-image">
        <h3>{{ product.name }}</h3>
        <p class="price">${{ product.price }}</p>
        <p>{{ product.description }}</p>
        <button @click="addToCart(product)">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<script>
import '../styles/products.css'

export default {
  name: 'Products',
  data() {
    return {
      products: [
        { id: 1, name: 'Wireless Headphones', price: 99.99, category: 'Electronics', 
          description: 'High-quality wireless headphones with noise cancellation.', 
          image: 'https://via.placeholder.com/300x200?text=Headphones' },
        { id: 2, name: 'Smart Watch', price: 199.99, category: 'Electronics', 
          description: 'Track your fitness and stay connected with this smart watch.', 
          image: 'https://via.placeholder.com/300x200?text=Smart+Watch' },
        { id: 3, name: 'Bluetooth Speaker', price: 79.99, category: 'Electronics', 
          description: 'Portable speaker with crisp sound quality.', 
          image: 'https://via.placeholder.com/300x200?text=Speaker' },
        { id: 4, name: 'Running Shoes', price: 89.99, category: 'Sports', 
          description: 'Comfortable running shoes for all terrains.', 
          image: 'https://via.placeholder.com/300x200?text=Shoes' },
        { id: 5, name: 'Yoga Mat', price: 29.99, category: 'Sports', 
          description: 'Non-slip yoga mat for your workouts.', 
          image: 'https://via.placeholder.com/300x200?text=Yoga+Mat' },
        { id: 6, name: 'Coffee Maker', price: 49.99, category: 'Home', 
          description: 'Make perfect coffee every morning.', 
          image: 'https://via.placeholder.com/300x200?text=Coffee+Maker' }
      ],
      searchQuery: '',
      selectedCategory: '',
      cart: []
    }
  },
  computed: {
    categories() {
      return [...new Set(this.products.map(product => product.category))];
    },
    filteredProducts() {
      return this.products.filter(product => {
        const matchesSearch = product.name.toLowerCase().includes(this.searchQuery.toLowerCase()) || 
                             product.description.toLowerCase().includes(this.searchQuery.toLowerCase());
        const matchesCategory = !this.selectedCategory || product.category === this.selectedCategory;
        return matchesSearch && matchesCategory;
      });
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product);
      alert(`${product.name} added to cart!`);
    }
  },
  mounted() {
    const productId = this.$route.query.product;
    if (productId) {
      const product = this.products.find(p => p.id === parseInt(productId));
      if (product) {
        setTimeout(() => {
          const element = document.querySelector(`[data-product-id="${productId}"]`);
          if (element) {
            element.scrollIntoView({ behavior: 'smooth' });
          }
        }, 100);
      }
    }
  }
}
</script>

