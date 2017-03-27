<template>
  <div class="container">
    <hero
      :title="heroTitle"
      :subtitle="heroSubtitle"
      :tel="heroTel"
      :navItems="heroNavItems"
      :image="heroImage"
      />
    <h1 class="h1" v-if="mainTitle">{{mainTitle}}</h1>
    <vue-markdown class="rte">{{firstRTEContent}}</vue-markdown>
    <testimonials :testimonials="testimonials" :image="testimonialImage" />
  </div>
</template>

<script>
import VueMarkdown from 'vue-markdown';
import Hero from './Hero';
import Testimonials from './Testimonials';

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
      heroImage: '/static/img/bg-hero.eec1bdc.jpg',
      mainTitle: 'Why Pilates?',
      firstRTEContent: 'Pilates is a series of slow controlled movements primarily to strengthen the core muscles that stabilise and support the spine, realign the body and correct postural problems.\n \n This is a line of text [with a link](https://pete.nai.sh "Title")',
      testimonials: [
        {
          id: '000',
          text: 'I was very apprehensive before coming to Laura’s classes, feeling that I was older and less flexible than most of her clients.  Her quiet explanation of each set of exercises and gentle coaxing soon had me reassured, confident and looking forward to the next class - so thank you very, very much',
          author: 'Lesley',
        },
      ],
      testimonialImage: '/static/img/bg-testimonials.eec1bdc.jpg',
    };
  },
  components: {
    Hero,
    VueMarkdown,
    Testimonials,
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
  &:before,
  &:after {
      content: '';
      display: table;
  }
  &:after {
      clear: both;
  }
}

.h1 {
  color: #404040;
  float: left;
  font-size: 72px;
  line-height: 1.2;
  margin: -20px 65px 0 120px;
  max-width: 254px;
  text-align: right;
  text-transform: lowercase;
  &:after {
    background: #80dcd0;
    border-radius: 10px;
    content: '';
    height: 10px;
    float: right;
    width: 55%;
  }
  + .rte {
    overflow: hidden;
    margin-left: 0;
  }
}

.rte {
  color: #404040;
  margin: 0 120px 15px;
  p {
    margin: 0 0 35px 0;
  }
  a {
    border-bottom: 3px solid transparent;
    color: #e75d64;
    text-decoration: none;
    transition: border .2s ease-out;
    &:hover {
      border-bottom-color: #e75d64;
      transition-duration: .1s;
    }
  }
}
</style>
