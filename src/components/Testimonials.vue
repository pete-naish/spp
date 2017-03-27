<template>
  <div class="testimonials" :style="style">
    <testimonial v-for="item in testimonials" :item="item" :key="item.id" />
  </div>
</template>

<script>
import Testimonial from './Testimonial';

export default {
  props: [
    'testimonials',
    'image',
  ],
  components: {
    Testimonial,
  },
  computed: {
    style() {
      return {
        backgroundImage: 'url(/static/img/bg-testimonials.ad47300.jpg)',
      };
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.testimonials {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
