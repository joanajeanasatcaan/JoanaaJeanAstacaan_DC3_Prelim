
<template>
<center>
    <div class="itemList">
        <h2>ITEM LIST</h2>
        <div class="products-container">
            <ProductItem
                v-for="product in products"
                :key="product.id"
                :product="product"
                @add-to-cart="handleAddToCart"
            />
        </div>
    </div>
    </center>
</template>

<script>
import ProductItem from './Item.vue';

export default {
    name: 'ProductList',
    components: {
        ProductItem,
    },
    props: {
        products: {
            type: Array,
            required: true,
        },
    },
    methods: {
        handleAddToCart(product) {
            console.log('Product added to cart:', product);
        }
    }
};
</script>

<style scoped>
.itemlist {
    padding: 20px;
   
}
.products-container {
    display: flex;
    justify-content: space-around;
    gap: 16px;
    
}
</style>
