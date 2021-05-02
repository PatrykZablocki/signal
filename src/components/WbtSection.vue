<template>
  <section class='wbt-section'>
    <div class="container">
        <div class="content">
            <h2 class="second-headline">
                Work better together
            </h2>
            <p class="paragraphe">
                Being a freelancer is a rollercoaster of emotions.
                We built Slate to keep your freelance business less stressful.
                <span class='desktop-text'>We'd love to show you what we're building...</span>
            </p>
          <div class="wrapper">
              <div class="bar" />
              <div class="info">
                  <p class="name">Facebook</p>
                  <p class="number">35,929</p>
              </div>
          </div>
          <PrimaryButton>Try For Free</PrimaryButton>
        </div>
    </div>
  </section>
</template>

<script>
import PrimaryButton from './Buttons/PrimaryButton'

export default {
    name: 'WbtSection',
    components: {
        PrimaryButton,
    },
}
</script>

<style lang='scss' scoped>
@import "../styles/colors.scss";

.wbt-section {
    background: $color-light-background;
    padding: 100px 0;
}

.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0 80px;
    max-width: 750px;
    margin: 0 auto;

    @media screen and (max-width: 499.98px) {
        padding: 0;
    }
}

h2 {
    margin-bottom: 18px;
}

.paragraphe {
    text-align: center;
    padding: 0 40px;
    margin-bottom: 60px;
    color: $color-second-text;

    .desktop-text {
        display: none;
    }

    @media screen and (min-width: 768px) {
        padding: 0;
        .desktop-text {
            display: unset;
        }
    }
}

.wrapper {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin-bottom: 40px;
}

.info {
    font-family: 'Roboto', sans-serif;
    font-size: 14px;
    display: flex;
    justify-content: space-between;

    .name {
        font-weight: 400;
        color: #505D6F;
    }

    .number {
         font-weight: 700;
         color: #505D70;
    }
}
.bar {
    width: 100%;
    height: 15px;
    background: #F3F5F8;
    border-radius: 9.5px;
    position: relative;
    margin-bottom: 7px;

    &::before {
        content: '';
        height: 100%;
        width: 70%;
        position: absolute;
        top: 0;
        left: 0;
        background: #0285E4;
        border-radius: inherit;
    }
}

</style>