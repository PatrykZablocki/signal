<template>
  <section class="newsletter-section">
      <div class="container">
          <div class="content">
                <div class="text-wrapper">
                  <h2 class="second-headline">
                      OpenType features and Variable fonts
                  </h2>
                  <p class="sub-heading">
                    Most calendars are designed for teams.
                    Slate is designed for freelancers who want a simple way to plan their schedule.
                  </p>
                </div>
                <div class="wrapper">
                    <input placeholder="Enter Your Address Email" />
                    <PrimaryButton class='button'>Subscribe</PrimaryButton>
                </div>
          </div>
          <img src='../assets/iphone-image.png' />
      </div>
  </section>
</template>

<script>
import PrimaryButton from './Buttons/PrimaryButton'

export default {
    name: 'NewsletterSection',
    components: {
        PrimaryButton,
    },
}
</script>

<style lang='scss' scoped>
@import "../styles/colors.scss";

.newsletter-section {
    background: $color-mute-background;
    padding-top: 120px;
    padding-bottom: 80px;
    overflow: hidden;
}

.container {
    display: grid;
    grid-template-columns: repeat(12, 1fr);

    .content {
        grid-column: span 12;
    }

    img {
        width: min(460px, 100% );
        grid-column: span 12;
        justify-self: center;
    }

    @media screen and (min-width: 768px) {

        .content {
            grid-column: 1/7;
        }

        img {
            width: 100%;
            grid-column: 7/13;
            margin-bottom: -300px;
            margin-top: -80px;
            margin-right: -30px;
            justify-self: end;
        }
    }
}



.text-wrapper {
    padding: 0 50px;

    h2 {
        padding: 0 25px;

        @media screen and (max-width: 420px) {
            padding: 0;
        }
    }

    .sub-heading {
        margin: 40px 0;
    }

    @media screen and (min-width: 768px) {
        padding: 0;

        h2 {
            padding: 0;
            text-align: start;
        }

        .sub-heading {
            text-align: start;
        }
    }
}

.wrapper {
    display: flex;
    flex-direction: column;
    row-gap: 12px;
    align-items: center;

    @media screen and (min-width: 768px) {
        flex-direction: row;
    }
}

input {
    border: 1px solid #D0D0D0;
    border-radius: 50px;
    background: $color-light-background;
    font-family: 'Roboto', sans-serif;
    font-weight: 700;
    font-size: 15px;
    letter-spacing: 0.2px;
    padding: 16px;
    width: min(380px, 100%);
    text-align: center;

    @media screen and (min-width: 768px) {
        text-align: start;
        width: 280px;
    }
}

.button {
    @media screen and (max-width: 767.98px) {
        width: min(380px, 100%);
        padding-top: 23px;
        padding-bottom: 23px;
    }

    margin-left: 8px;
}

//focus
input{
    outline: none;

    &:focus {
        border-width: 2px;
        border-color:  $color-dark-background;
    }
}
</style>