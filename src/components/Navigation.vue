<template>
    <nav class='navigation'>
        <div class="content">
            <a href="/#" class='logo'>
                <img class='logo-image' src='../assets/signal-dark-logo.svg'/>
            </a>
            <div class="nav-items" :class="{'nav-items--open': isOpen}">
                <a href='#' class="nav-item">Home</a>
                <a href='#' class="nav-item">Product</a>
                <a href='#' class="nav-item">About</a>
                <a href='#' class="nav-item">Contact</a>
            </div>
            <div class="wrapper">
                <PrimaryButton class="button">Sign Up</PrimaryButton>
                <div @click="isOpen = !isOpen" class="hamburger">
                    <img class='hamburger-icon' src='../assets/hamburger-icon.svg' />
                </div>
           </div>
        </div>
    </nav>
</template>

<script>
import PrimaryButton from './Buttons/PrimaryButton'

export default {
    name: "Navigation",
    components: {
        PrimaryButton,
    },
    data: () => {
        return {
            isOpen: false,
        }
    },
}
</script>

<style lang="scss" scoped>
@import "../styles/colors.scss";

.navigation {
    //background: $color-light-background;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 99;
    padding: 14px 16px;

    &::before {
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        background: $color-light-background;
        z-index: -1;
    }

    @media screen and (min-width: 768px) {
        padding: 24px 16px;
    }

}

.content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1024px;
    margin: 0 auto;
}

.logo {
    display: flex;
}

.nav-items {
    z-index: -2;
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    top: 0;
    left: 0;
    padding-top: 80px;
    padding-bottom: 20px;
    width: 100%;
    background: $color-light-background;
    transform: translateY(-100%);

    &--open {
        transform: translateY(0);
    }

    @media screen and (min-width: 768px) {
        position: relative;
        width: auto;
        z-index: 0;
        background: transparent;
        padding: 0;
        flex-direction: row;
        justify-content: center;
        transform: translateX(0);
    }
}

.nav-item {
    color: $color-first-text;
    text-decoration: none;
    padding: 10px;
    margin: 0 15px;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0.2px;
}

.wrapper {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    width: 100%;

    @media screen and (min-width: 768px) {
        width: auto;
    }
}

.button {
    @media screen and (max-width: 420px) {
        padding: 0 16px;
        height: 52px;
        width: 100%;
        max-width: 150px;
        margin-left: 16px;
    }
}

.hamburger {
    cursor: pointer;
    margin-left: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 42px;
    height: 32px;

    img {
        width: 26px;
        height: 16.67px;
    }

    @media screen and (min-width: 768px) {
        display: none;
    }

    @media screen and (max-width: 420px) {
        margin-left: 8px;
    }
}

</style>