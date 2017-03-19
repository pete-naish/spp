<template>
  <nav class="nav-primary">
    <ul class="nav-primary__items">
      <li class="nav-primary__item" v-for="item in navItems">
        <a class="nav-primary__link" :href="formatAnchor(item.anchor)">{{item.text}}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: [
    'navItems',
  ],
  methods: {
    formatAnchor(anchor) {
      return `#${anchor}`;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.nav-primary {
  float: right;
}

.nav-primary__items {
  margin: 0;
}

.nav-primary__item {
  float: left;
  list-style: none;
  & + & {
    margin-left: 20px;
  }
}

.nav-primary__link {
  border-bottom: 3px solid transparent;
  color: #fff;
  text-decoration: none;
  transition: border .2s ease-out;
  &:hover {
    border-bottom-color: #fff;
    transition-duration: .1s;
  }
}

</style>
