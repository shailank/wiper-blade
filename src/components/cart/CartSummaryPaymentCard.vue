<template>
    <div class="cart-item-card">
        <h3>Total Amount: ${{ cart_total.toFixed(2) }}</h3>

        <button class="view-product-button" style="width:100%;">Pay Now</button>
    </div>
</template>

<script>
    export default {
        computed: {
            cart_total() {
                return this.$store.getters.cartItems.reduce((a, b) => a + (b.price * b.quantity), 0)
            }
        }
    }
</script>