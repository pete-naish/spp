<template>
  <div class="testimonials" :style="style">
    <testimonial
      v-for="item in testimonials"
      :item="item"
      :key="item.id"
    />
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
        backgroundImage: `url(${this.image})`,
      };
    },
  },
  mounted() {
    setTimeout(() => {
      this.testimonials[0].show = true;
    }, 1000);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.testimonials {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  margin-bottom: 55px;
  position: relative;
  &:before,
  &:after {
    color: #e75d64;
    font-family: 'Libre Baskerville', serif;
    font-size: 192px;
    line-height: 1;
    position: absolute;
  }
  &:before {
    content: '\201C';
    left: 25px;
    top: -40px;
  }
  &:after {
    bottom: -172px;
    content: '\201D';
    right: 25px;
  }
}
</style>
