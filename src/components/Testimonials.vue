<template>
  <div class="testimonials" :style="style">
    <button @click="prev">Prev</button>
    <button @click="next">Next</button>
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
    testimonialCount() {
      return this.testimonials.length - 1;
    },
  },
  data() {
    return {
      current: this.testimonials.findIndex(item => item.show),
    };
  },
  mounted() {
    setTimeout(() => {
      // console.log('this.testimonialCount', this.testimonialCount);
      console.log(this.testimonials.findIndex(item => item.show));
    }, 1000);
  },
  methods: {
    next() {
      const next = this.testimonials[this.current + 1] || this.testimonials[0];

      this.hideCurrent();

      next.show = true;
      this.current = next;
    },
    prev() {
      const prev = this.testimonials[this.current - 1]
        || this.testimonials[this.testimonialCount()];

      this.hideCurrent();
      prev.show = true;
      this.current = prev;
    },
    hideCurrent() {
      console.log(this.testimonials[this.current]);
      this.testimonials[this.current].show = false;
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

button {
  float: right;
}
</style>
