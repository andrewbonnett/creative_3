<template>

<div class="cart-page-container">
  <p v-if="this.$root.$data.cart.length === 0" style="text-align: center;">No items in cart.</p>
    <div v-else>
      <div class="cart-heading">Your Cart</div>

      <hr>
        <div class="row">
          <div class="cart-text col-sm">Item<a v-if="this.$root.$data.cart.length > 1">s</a></div>
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

img {
  width: 100%;
}

.cart-heading {
  text-align: left;
  font-size: 30px;
  color: black;
  font-family:"Arial Black", Gadget, sans-serif;
}

.cart-page-container {
  margin: auto;
  padding-top: 35px;
  padding-bottom: 85px;
  background-color: white;
  width:65%;
}

.cart-text {
  margin: auto;
  font-size: 24px;
}

.cart-text-2 {
  font-size: 24px;
  text-align: right;
  margin: auto;
}

</style>
