<template>
  <div class="hero">
    <a class="hero__cta" :href="heroTelForHref">Call {{tel}}</a>
    <navigation :navItems="navItems"></navigation>
    <h1 class="hero__title">{{title}}</h1>
    <h2 class="hero__subtitle">{{subtitle}}</h2>
  </div>
</template>

<script>
import Navigation from './Navigation';

export default {
  props: [
    'title',
    'subtitle',
    'tel',
    'navItems',
  ],
  components: {
    Navigation,
  },
  computed: {
    heroTelForHref() {
      return `tel:${this.tel.replace(/\s/g, '')}`;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.hero {
  background-image: url(../assets/img/bg-hero.jpg);
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #fff;
  padding: 40px;
}

.hero__title,
.hero__subtitle {
  font-family: 'Libre Baskerville', serif;
  margin: 0;
  text-align: center;
  text-shadow: 0px 0px 30px rgba(0, 0, 0, .35);
}

.hero__title {
  font-size: 82px;
  font-weight: 400;
  margin-top: 290px;
  text-transform: uppercase;
}

.hero__subtitle {
  font-size: 42px;
  margin-bottom: 250px;
}

.hero__cta {
  border-bottom: 3px solid transparent;
  color: inherit;
  font-size: 32px;
  text-decoration: none;
  transition: border .2s ease-out;
  &:hover {
    border-bottom-color: #fff;
    transition-duration: .1s;
  }
}
</style>
