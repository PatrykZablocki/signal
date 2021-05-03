<template>
  <Navigation :isOpen="isOpen" v-on:menuState="menuState" />
  <div ref='page'>
    <HeaderSection :mobileView="mobileView" />
    <StatsSection />
    <NewsletterSection />
    <WbtSection />
    <Footer />
  </div>
</template>

<script>
import Navigation from './components/Navigation'
import HeaderSection from './components/HeaderSection.vue'
import StatsSection from './components/StatsSection'
import NewsletterSection from './components/NewsletterSection'
import WbtSection from './components/WbtSection'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Navigation,
    HeaderSection,
    StatsSection,
    NewsletterSection,
    WbtSection,
    Footer,
  },
  data: () => {
    return {
        mobileView: Boolean,
        isOpen: false,
    };
  },
  methods: {
    handleView() {
        this.mobileView = window.innerWidth < 768 ;
    },
    menuState() {
      this.isOpen = !this.isOpen;
      if(this.isOpen) {
        this.$refs.page.addEventListener('click', () => {
          this.isOpen = false;
        });
      }
    },
  },
  created() {
    this.handleView();
    window.addEventListener('resize', this.handleView);
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@400;700&family=Roboto:wght@400;700&display=swap');
@import "./styles/colors.scss";

* {
    font-family: 'Nunito Sans', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.only-mobile {
  @media screen and (min-width: 768px) {
    display: none;
  }
}

.container {
  margin-left: auto;
  margin-right: auto;
  padding: 0 30px;
  max-width: 1060px;

  @media screen and (max-width: 399.98px) {
    padding: 0 15px;
  }
}

.headline {
  font-family: 'Nunito Sans', sans-serif;
  font-weight: 700;
  font-size: 54px;
  line-height: 64px;
  text-align: center;
  letter-spacing: 0.2px;
}

.second-headline {
  font-family: 'Nunito Sans', sans-serif;
  font-weight: 700;
  font-size: 40px;
  line-height: 48px;
  text-align: center;
  letter-spacing: 0.2px;
}

.sub-heading {
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  color: $color-second-text;
  font-size: 20px;
  line-height: 28px;
  text-align: center;
  letter-spacing: 0.2px;
}

.title {
  font-family: 'Nunito Sans', sans-serif;
  font-weight: 700;
  font-size: 24px;
  line-height: 32px;
  letter-spacing: 0.1px;
}

.paragraphe {
  font-family: 'Nunito Sans', sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0.2px;
}
</style>