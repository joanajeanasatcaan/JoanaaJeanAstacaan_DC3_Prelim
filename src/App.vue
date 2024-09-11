<template>
  <div id="app">
    <!-- <h1>Welcome to the Store</h1> -->
    <itemList :products="products" @checkout="handleCheckout" />
  </div>
</template>

<script>
import itemList from './components/ItemList.vue';

export default {
  name: 'App',
  components: {
    itemList,
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Compact Powder', price: 260, image: 'powder.png' },
        { id: 2, name: 'Powder Blush', price: 199, image: 'blush.webp' },
        { id: 3, name: 'Lipstick', price: 89, image: 'lipstick.webp' },
      ],
    };
  },
  methods: {
    handleCheckout(product) {s
      alert(`You checked out ${product.name} for $${product.price}`);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: 'Comic Sans MS', 'Avenir', 'Helvetica', 'Arial', sans-serif; /* Playful font */
  text-align: center;
  margin-top: 60px;
  background-color: #fce4ec;
  color: #ff4081; 
  padding: 20px;
  border-radius: 15px; 
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 2.5rem;
  color: #e91e63; 
}

button {
  background-color: #ffb6c1; 
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 10px 0;
  border-radius: 10px; /* Rounded button corners */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Button shadow */
  transition: background-color 0.3s ease; /* Smooth hover effect */
}

button:hover {
  background-color: #ff69b4; /* Darker pink on hover */
}

img {
  max-width: 100px;
  border-radius: 10px; /* Rounded image edges */
  margin-bottom: 10px;
}

.product {
  background-color: #ffe4e1; /* Very light pink for product containers */
  padding: 20px;
  margin: 10px;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.product-name {
  font-size: 1.5rem;
  color: #ff1493; /* Bright pink for product names */
}

.product-price {
  font-size: 1.2rem;
  color: #ff4081; /* Softer pink for product prices */
}

</style>

