<template>
<div id="app">

<!-- NAVBAR-->
  <nav class="navbar sticky-top navbar-expand-lg navbar-light bg-primary">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home<span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="pages/shop.html">Shop</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="pages/cart.html">Cart</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="pages/about.html">About</a>
        </li>
      </ul>
    </div>
  </nav>
  <!-- END NAVBAR-->

  <!-- LOGO CONTAINER -->
  <div id="logo" class="logo-container">
    <img src="images/logo.jpeg" width="300" style="text-align: center;">
  </div>
  <!-- END LOGO CONTAINER -->



  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.jpeg">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/love.png">
          <p> {{ numCartItems }} items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />


</div>
</template>

<script>
export default {
  computed: {
    numCartItems() {
      return this.$root.$data.cart.length;
    },
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

container {
  margin: 50px 100px;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>
