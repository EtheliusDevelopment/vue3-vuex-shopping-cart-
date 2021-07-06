<template>
  <div id="nav">
    <router-link :class="{active : $route.name === 'Home'}" to="/">Home</router-link> |
    <router-link :class="{active : $route.name === 'Cart'}" to="/cart">Cart</router-link>
  </div>
  <router-view/>
</template>



<style lang="scss">

body{
  background-color: #1d73c931;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #b542b9;
    }
  }
}

#nav{
  padding: 10px;
  width: 100%;
  height: 30px;
  background-color: white;
  line-height: 30px;
}

.active{
  color: darkgray !important;
}
</style>
