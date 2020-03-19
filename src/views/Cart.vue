<template>

<div class="cart-page-container">
  <p v-if="this.$root.$data.cart.length === 0" style="text-align: center;">No items in cart.</p>
    <div v-else>
      <div class="cart-heading">Your Cart</div>

      <hr>
        <div class="row">
          <div class="cart-text col-sm">Item(s)</div>
          <div class="cart-text col-sm-6">
          </div>
          <div class="cart-text-2 col-sm">
            Price
          </div>
          <div class="cart-text-2 col-sm">Qty</div>
        </div>
      <hr>

      <div v-for="item in this.$root.$data.cart" :key="item.id">
        <div class="row">
          <div class="col-sm">
            <img :src="'/images/products/'+item.image" width="100%">
          </div>
          <div class="cart-text col-sm-6">
            {{item.name}}
          </div>
          <div class="cart-text-2 col-sm">
            {{item.price}}
          </div>
          <div class="cart-text-2 col-sm">
            1  <!--FIX QUANTITY -->
            <button class="btn btn-outline-secondary" @click="removeFromCart(item.id)">Remove Item</button>
          </div>
        </div>
        <hr>
      </div>

  </div>
</div>

</template>

<script>
export default {
  name: 'Cart',
  methods: {
    removeFromCart(id) {
      for (let i = 0; i < this.$root.$data.cart.length; i++) {
        if (this.$root.$data.cart[i].id === id) {
          this.$root.$data.cart.splice(i,1);
        }
      }
    }
  },
}
</script>

<style scoped>

.product img {
  width: 200px;
}

</style>
