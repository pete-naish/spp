<template>
  <footer class="footer">
    <p class="footer__copy">{{copy}}</p>
    <img
      v-for="image in images"
      :src="image.path"
      class="footer__image"
    />
  </footer>
</template>

<script>

export default {
  props: [
    'images',
    'copy',
  ],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.footer {
  color: #fff;
  background-color: #404040;
  padding: 20px 40px;
  &:before,
  &:after {
    content: " ";
    display: table;
  }

  &:after {
    clear: both;
  }
}

.footer__copy {
  float: left;
  font-size: 22px;
  margin: 25px 0 0;
}

.footer__image {
  float: right;
  margin-left: 35px;
}
</style>
