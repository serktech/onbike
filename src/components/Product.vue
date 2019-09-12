<template>
    <div class="card my-3 shadow bg-white rounded">
        <div class="card-body">
            <h5 class="text-center card-title">{{product.name}}</h5>
            <p class="text-center text-muted card-text">{{product.product_type}}</p>
            <img
                    v-bind:src="product.image"
                    class="img-fluid rounded card-img-top"
                    alt="image"
            >
            <p class="text-center text-muted card-text display-4">${{Number(product.price).toFixed(2)}}</p>
            <button :disabled="isInCart" @click="$emit('add-to-cart',product)" class="btn btn-primary form-control">
                {{isInCart ? 'Added to cart': 'Add to Cart'}}
            </button>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['product', 'isInCart']
    }
</script>
