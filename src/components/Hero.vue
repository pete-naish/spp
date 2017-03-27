<template>
  <div class="hero" :style="style">
    <a class="hero__cta" :href="heroTelForHref">Call {{tel}}</a>
    <navigation :navItems="navItems" />
    <h1 class="hero__title">{{title}}</h1>
    <h2 class="hero__subtitle">{{subtitle}}</h2>
    <span class="hero__clip" />
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
    'image',
  ],
  components: {
    Navigation,
  },
  computed: {
    heroTelForHref() {
      return `tel:${this.tel.replace(/\s/g, '')}`;
    },
    style() {
      return {
        backgroundImage: `url(${this.image})`,
      };
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.hero {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #fff;
  margin-bottom: 40px;
  overflow: hidden;
  padding: 40px;
  position: relative;
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
  text-decoration: none;
  transition: border .2s ease-out;
  &:hover {
    border-bottom-color: #fff;
    transition-duration: .1s;
  }
}

.hero__clip {
  bottom: 0;
  height: 80px;
  left: 0;
  overflow: hidden;
  position: absolute;
  width: 100%;
  &:after {
    background: radial-gradient(ellipse at center, transparent 63%, #fff 50%, #fff 50%);
    bottom: 0;
    content: '';
    height: 390%;
    left: -20%;
    position: absolute;
    width: 140%;
  }
}
</style>
