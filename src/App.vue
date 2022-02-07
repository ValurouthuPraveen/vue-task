<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style scoped> 
/* .alert-dismissible .close  */
/* #app > div.home > div > div > div > button */
.close{
  position: absolute;
  top:0px;
  right: 5px;
  background-color: transparent;
  border-color: transparent;
  font-size: xx-large;
}
.close:hover{
  font-weight: bold;
}

/* .modal-header */

#modal-lg___BV_modal_header_, #modal-lg___BV_modal_footer_{
    display: none;
}

.modal-body {
    background: rgb(224, 216, 216);
    opacity: 1;
}

/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
