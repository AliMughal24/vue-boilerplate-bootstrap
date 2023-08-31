<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
.text-color {
  color: #6697e0;
}
.multiselect__tags {
  border: none !important;
}
.form-control {
  border: none !important;
  color: gold !important;
}
.review-rating .b-icon {
  width: 1.5rem !important;
  height: 1.5rem !important;
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
      color: #42b983;
    }
  }
}
</style>
