<template>
  <blockquote
    class="testimonial__item"
    :class="{ 'testimonial__item--active': item.show }"
  >
    {{item.text}} - {{item.author}}
  </blockquote>
</template>

<script>

export default {
  props: [
    'item',
  ],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.testimonial__item {
  color: #fff;
  font-family: 'Libre Baskerville', serif;
  font-size: 30px;
  line-height: 1.6;
  margin: 0;
  max-width: 630px;
  padding: 80px 40px;
  text-align: justify;
  opacity: 0;
  transition: opacity .4s ease-out;
}

.testimonial__item--active {
  opacity: 1;
}
</style>
