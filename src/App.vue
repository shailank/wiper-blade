<template>
  <div class="topnav" id="myTopnav">
    <router-link :class="{active: $route.name === 'Home'}" to="/">Product</router-link> 
    <router-link :class="{active: $route.name === 'Cart'}" to="/cart">Cart ({{this.$store.getters.cartItems.length}})</router-link>
	
	
  </div>
  <router-view />
</template>

<script>
  export default {
    mounted() {
      this.$store.commit('updateCartFromLocalStorage')
    },

  }
</script>

<style lang="scss">
.topnav {
  overflow: hidden;
  background-color: #333;
}

.topnav a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: #ddd;
  color: black;
}

.topnav a.active {
  background-color: #04AA6D;
  color: white;
}

.topnav .icon {
  display: none;
}

@media screen and (max-width: 600px) {
  .topnav a:not(:first-child) 
  .topnav a.icon {
    float: right;
    display: block;
  }
}

@media screen and (max-width: 600px) {
  .topnav.responsive {position: relative;}
  .topnav.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

body {
  background-color: rgb(245, 245, 245);
}

#nav {
  padding: 10px;
  width: 100%;
  height: 30px;
  background-color: white;
  line-height: 30px;


  a {
    font-weight: bold;
    color: darkgray ;
    text-decoration: none;
    margin: 0 5px 0 5px;
    font-size: 1.25rem;

    &.active {
      color:#2c3e50;
    }
  }
}

.text-center {
  text-align: center;
}
</style>
