<template>
    <section class='header-section'>
        <div class="container content">
            <div class="text-wrapper">
                <h1 :class="[ mobileView ? 'second-headline' : 'headline' ]" >
                    Lightning <br v-if="mobileView"/> fast prototyping
                </h1>
                <p class='sub-heading'>
                    Most calendars are designed for teams.
                    <br/>
                    Slate is designed for freelancers who want a simple way to plan their schedule.
                </p>

                <img class='icon icon--one' src="../assets/header-icon1.svg" />
                <img class='icon icon--two' src="../assets/header-icon2.svg" />
                <img class='icon icon--three' src="../assets/header-icon3.svg" />
                <img class='icon icon--four' src="../assets/header-icon4.svg" />
                <img class='icon icon--five' src="../assets/header-icon5.svg" />
            </div>
            <PrimaryButton class='button'>Try For Free</PrimaryButton>
            <img class='header-image' src="../assets/header-image.png" />
        </div>
    </section>
</template>

<script>
import PrimaryButton from './Buttons/PrimaryButton'

export default {
    name: 'HeaderSection',
    components: {
        PrimaryButton,
    },
    props: {
        mobileView: Boolean,
    },
}
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";

.header-section {
    padding-top: 80px;
    position: relative;
    background: linear-gradient(170deg,
     $color-light-background, $color-light-background 72%,
     $color-dark-background 72.2%, $color-dark-background
     );

    @media screen and (min-width: 768px) {
        padding-top: 100px;
    }

}

.content {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.text-wrapper {
   position: relative;
   display: flex;
   flex-direction: column;
   align-items: center;
   padding: 87px 0;

   p {
       max-width: 500px;

        @media screen and (min-width: 768px) {
            max-width: 580px;
        }
   }

   br {
       display: none;

       @media screen and (min-width: 460px) and (max-width: 768px) {
           display: unset;
       }
   }
}

h1 {
    color: $color-first-text;
    margin-bottom: 16px;
}

.button {
    width: fit-content;
    margin-bottom: 100px;
    padding-left: 80px;
    padding-right: 80px;
    z-index: 1;

    @media screen and (min-width: 768px) {
        margin-bottom: 0;
    }
}

.header-image {
    max-width: 100%;
    margin-bottom: 50px;
}

.icon {
    position: absolute;

    &--one {
        width: 16px;
        height: 16px;
        bottom: 15%;
        left: 15%;
    }

    &--two {
        width: 18px;
        height: 18px;
        bottom: -10%;
        left: 0;
    }

    &--three {
        width: 24px;
        height: 24px;
        bottom: 10%;
        right: 10%;
    }

    &--four {
        width: 30px;
        height: 30px;
        bottom: -30%;
        right: 30%;
    }

    &--five {
        width: 26px;
        height: 26px;
        bottom: -20%;
        right: 5%;
    }

    @media screen and (min-width: 1024px) {
        &--one {
            width: 34px;
            height: 33px;
            left: -10%;
        }

        &--two {
            width: 38px;
            height: 38px;
            bottom: -50%;
            left: -20%;
        }

        &--three{
            width: 45px;
            height: 45px;
            bottom: -5%;
            right: -10%;
        }

        &--four {
            width: 60px;
            height: 60px;
            bottom: -50%;
            right: 15%;
        }

        &--five {
            width: 55px;
            height: 55px;
            right: -18%;
            bottom: -65%;
        }
    }
}
</style>