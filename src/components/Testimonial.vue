<template>
  <blockquote class="testimonial__item">
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
  position: relative;
  quotes: "\201C" "\201D" "\2018" "\2019";
  text-align: justify;
  &:before,
  &:after {
    color: #e75d64;
    font-size: 192px;
    line-height: 1;
    position: absolute;
  }
  &:before {
    content: open-quote;
    left: 25px;
    top: -40px;
  }
  &:after {
    bottom: -172px;
    content: close-quote;
    right: 25px;
  }
}
</style>
