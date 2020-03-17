<template>
<div class="wrapper">
  <p style="text-align: center;" v-show="this.$root.$data.cart.length === 0">No items in cart.</p>
    <div class="row product" v-for="item in this.$root.$data.cart" :key="item.id">
      <div class="col">
        <div class="image">
        <img :src="'/images/products/'+item.image">
        </div>
      </div>
      <div class="col">
        <h3>{{item.name}}</h3>
        <p>{{item.country}}</p>
      </div>
      <div class='col'>
        <div class="price">
          <h4>{{item.price}}</h4>
          <button class="btn btn-outline-secondary" @click="removeFromCart(item.id)">Remove Item</button>
        </div>
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
