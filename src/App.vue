<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>

<style lang="scss">
body {
  box-sizing: border-box;
  font-family: 'Nunito', sans-serif;
  margin: 0;
  padding: 0;
}

#app {
  background-image: url(assets/img/bg-page.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  padding: 50px 20px;
}
</style>
