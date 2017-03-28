<template>
  <div class="contact-form" :style="style">
    <h2 class="contact-form__title">{{title}}</h2>
    <h3 class="contact-form__subtitle">{{subtitle}}</h3>
    <Formspree />
  </div>
</template>

<script>
import Formspree from './Formspree';

export default {
  props: [
    'image',
    'title',
    'subtitle',
  ],
  computed: {
    style() {
      return {
        backgroundImage: `url(${this.image})`,
      };
    },
  },
  components: {
    Formspree,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.contact-form {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #fff;
  margin: 0;
  padding: 40px;
  text-align: center;
}

.contact-form__title {
  font-size: 50px;
  line-height: 1;
  margin: 5px 0 25px 0;
  text-transform: lowercase;
}

.contact-form__subtitle {
  font-size: 32px;
  margin: 0 0 65px 0;
}
</style>
