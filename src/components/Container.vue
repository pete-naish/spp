<template>
  <div class="container">
    <hero
      :title="heroTitle"
      :subtitle="heroSubtitle"
      :tel="heroTel"
      :navItems="heroNavItems"
      ></hero>
  </div>
</template>

<script>
import Hero from './Hero';

export default {
  data() {
    return {
      heroTitle: 'Simply Pure Pilates',
      heroSubtitle: 'by Laura Jeffs',
      heroTel: '07710 408974',
      heroNavItems: [
        {
          text: 'Why pilates?',
          anchor: 'why-pilates',
        },
        {
          text: 'Classes',
          anchor: 'classes',
        },
        {
          text: 'Contact',
          anchor: 'contact',
        },
      ],
    };
  },
  components: {
    Hero,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.container {
  background-color: #fff;
  box-shadow: 0px 0px 30px 0px rgba(0, 0, 0, 1);
  margin: 0 auto;
  max-width: 1200px;
  min-height: 100vh;
}
</style>
