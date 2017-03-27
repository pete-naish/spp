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
  font-size: 32px;
  margin: 0;
  padding: 0;
}

#app {
  background-attachment: fixed;
  background-image: url(assets/img/bg-page.jpg);
  background-position: center top;
  background-repeat: no-repeat;
  background-size: cover;
  overflow: hidden;
  padding: 50px 20px;
}
</style>
