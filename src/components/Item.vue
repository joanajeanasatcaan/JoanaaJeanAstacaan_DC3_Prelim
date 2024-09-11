<template>
    <div class="item">
        <img :src="product.image" alt="Product image" class="product-image" />
        <h3>{{ product.name }}</h3>
        <p>Price: ₱{{ product.price }}</p>
        <button @click="addToCart">Add to Cart</button>
    </div>
</template>

<script>
export default {
    name: 'ProductItem',
    props: {
        product: {
            type: Object,
            required: true,
        },
    },
    methods: {
        addToCart() {
            this.$emit('add-to-cart', this.product);
        }
    }
};
</script>

<style scoped>
.item {
    width: 200px; 
    text-align: center;
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 16px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    box-sizing: border-box;

}

.product-image {
    width: 100%; 
    height: 150px; 
    object-fit: cover;
    margin-bottom: 12px;
}

button {
    background-color: #42b983;
    color: white;
    border: none;
    padding: 8px 16px;
    cursor: pointer;
    font-size: 14px;
}

button:hover {
    background-color: #349a76;
}
</style>
