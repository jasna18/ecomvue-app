<template>
  <div id="app">
    <nav class="navbar">
    <Header/>
    </nav>
    <router-view/>
      <Footer/>
  </div>
</template>
<script>
import Header from './components/layout/Header.vue'
import Footer from './components/layout/Footer.vue'
import './styles/main.css';

export default {
  name: 'App',
  components: { Header, Footer }
}
</script>
 <!-- applied to all globally -->
<!-- Global styles (applies to entire app) we should import like body ,h1,titles-->
<!-- <style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
}
</style> -->

<!-- Scoped styles (only for App.vue) its only for App.vue -->
<!-- <style scoped>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
   -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style> -->
<!-- <style scoped src="@/styles/main.css"></style> applied to App.vue-->

