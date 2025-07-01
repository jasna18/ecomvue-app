# vue-app
A simple ecommerce vue-application with laravel backend
The app has 4 pages - home about products contact
the wend route loads the vue-app
with api route the products are given in a  static json format
added the router 
fetch the products to the vue-app with axios api

### directory structure 
laravel-app/
├── bootstrap/app.php
├── routes/
│   ├── api.php 
│   └── web.php
├── app/
│   └── Http/Controllers/
│       └── PageController.php
vue-app/
├── src(js)/
│   ├── App.vue
│   ├── components/
│   │   ├── Header.vue
│   │   ├── Footer.vue
│   │   └── pages/
│   │       ├── Home.vue
│   │       ├── About.vue
│   │       ├── Products.vue
│   │       └── Contact.vue
│   ├── router/
│   │   └── index.js
│   └── app.js (main.js)
 ### here the laravel controller loads the vue-app
 app.js is the main entry point to load the vue 
 ## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
