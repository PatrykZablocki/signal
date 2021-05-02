<template>
  <section class='stats-section'>
    <div class="container">
        <div class="content">
            <h2 class="second-headline">
                Fastest way <br class="only-mobile" /> to navigate
            </h2>
            <div class="cards">
                <div class="card card--one">
                    <img class='icon' src="../assets/stats-icon1.svg" />
                    <h4 class="title">Design with real data</h4>
                    <p class="paragraphe">
                        Ever wondered if you're too reliant on a client for work?
                        Slate helps you identify .
                    </p>
                    <div class="websites">
                        <div class="website">
                            <div class="stats">
                                <p class="name">Facebook</p>
                                <p class="number">35,929</p>
                            </div>
                            <div class="bar bar--facebook" />
                        </div>
                        <div class="website">
                            <div class="stats">
                                <p class="name">Twitter</p>
                                <p class="number">28,854</p>
                            </div>
                            <div class="bar bar--twitter" />
                        </div>
                        <div class="website">
                            <div class="stats">
                                <p class="name">Behance</p>
                                <p class="number">1,843</p>
                            </div>
                            <div class="bar bar--behance" />
                        </div>
                        <div class="website">
                            <div class="stats">
                                <p class="name">Instagram</p>
                                <p class="number">49,943</p>
                            </div>
                            <div class="bar bar--instagram" />
                        </div>
                    </div>
                </div>
                 <div class="card card--two">
                    <img class='icon' src="../assets/stats-icon2.svg" />
                    <h4 class="title">Work at the speed of thought.</h4>
                    <p class="paragraphe">
                        Ever wondered if you're too reliant on a client for work?
                        Slate helps you identify .
                    </p>
                    <img class="chart" src="../assets/stats-chart-icon.svg" >
                </div>
            </div>
            <PrimaryButton class="white">Try For Free</PrimaryButton>
        </div>
    </div>
  </section>
</template>

<script>
import PrimaryButton from './Buttons/PrimaryButton'

export default {
    name: "StatsSection",
    components: {
        PrimaryButton,
    },
}
</script>

<style lang='scss' scoped>
@import "../styles/colors.scss";

.stats-section {
    background: $color-dark-background;
    width: 100%;
    padding: 50px 0;
}

.content {
    display: flex;
    flex-direction: column;
    align-items: center;

    h2 {
        color: $color-light-text;
    }
}

.cards {
    width: 100%;
    margin-top: 70px;
    margin-bottom: 70px;
    row-gap: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;


    @media screen and (min-width: 960px) {
        flex-direction: row;
        column-gap: 120px;
        justify-content: center;
    }
}

.card {
    background: $color-light-background;
    padding: 40px;
    border-radius: 10px;
    width: 372px;
    max-width: 100%;

    .icon {
        margin-bottom: 10px;
    }

    h4 {
        max-width: 220px;
        margin: 25px 0;
    }

    .paragraphe {
        color: $color-second-text;
        margin: 25px 0;
        max-width: 260px;
    }

    &--two {
        .icon {
            margin-bottom: 30px;
        }
    }
}

.websites {
    margin-bottom: 40px;
}

.website {
    margin-top: 12px;
    margin-bottom: 12px;

    .stats {
        display: flex;
        justify-content: space-between;
        margin-bottom: 4px;
    }
    .name, .number {
        font-family: 'Roboto', sans-serif;
        font-size: 14px;
        line-height: 24px;
    }

    .name {
        color: #505D6F;
        font-weight: 400;
    }
    .number {
        color: #505D70;
        font-weight: 700;
    }

    .bar {
        width: 100%;
        height: 6px;
        background: #F3F5F8;
        border-radius: 9.5px;
        position: relative;

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            border-radius: inherit;
        }

        &--facebook {
            &::before {
                width: 50%;
                background: #2CD9C5;
            }
        }

        &--twitter {
            &::before {
                width: 28%;
                background: #2D99FF;
            }
        }

        &--behance {
            &::before {
                width: 80%;
                background: #826AF9;
            }
        }

        &--instagram {
            &::before {
                width: 9%;
                background: #FFE700;
            }
        }
    }
}

.chart {
    margin-top: 25px;
    display: flex;
    margin-left: auto;
    margin-right: auto;
    max-width: 100%;
}
</style>