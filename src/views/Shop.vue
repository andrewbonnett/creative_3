<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" />
      </form>
    </div>
  </div>
  <div class="sidebar-helper">
    <div class="sidebar">
      <h2>Men's</h2>
      More filters coming soon to Moonstone.
      <hr/>
      <span class="bucket-heading">Category</span>
      <ul>
          <li class="li-sidebar">New Arrivals</li>
          <li class="li-sidebar">Popular</li>
          <li class="li-sidebar">Shirts</li>
          <li class="li-sidebar">Swimwear</li>
          <li class="li-sidebar">Accessories</li>
      </ul>
    </div>
    <div class="main">
      <ProductList :products="products" />
    </div>
  </div>
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Home',
  components: {
    ProductList
  },
  data() {
  return {
    searchText: '',
  }
  },
  computed: {
  products() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText) >= 0);
  }
  },
}
</script>

<style>
.sidebar-helper {
    display: flex;
    justify-content: space-between;
}

.main {
    width: 75%;
    height: 150vh;
    padding-top: 20px;
    margin-bottom: 50px;
    margin-left: 20px;
    margin-right: 20px;
}

.sidebar {
    width: 25%;
    height: 100%;
    position: sticky!important;
    border-right: solid .5px #E6E6E6;
    padding-top: 20px;
    margin-left: 20px;
    top: 0!important;
    z-index: 1;
}

#shop body {
    height: 100%;
}

.bucket-heading{
    display: block;
    border-bottom: 1px solid #ccc;
    padding-bottom: 10px;
    width: 180px;
    font-family: "Arial Black", Gadget, sans-serif
}

.li-sidebar{
    font-size: .9375em;
    font-family: Arial, Helvetica, sans-serif;
    margin-top: 10px;
}

<!---------------------->
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
</style>
