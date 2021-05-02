<template>
  <div class="footer">
      <div class="content">
        <a href='/#'>
          <img src="../assets/signal-light-logo.svg" />
        </a>
        <div class="socials-wrapper">
          <img class='twitter' src="../assets/twitter-icon.svg" />
          <img class='facebook' src="../assets/facebook-icon.svg" />
          <img class='linkedin' src="../assets/linkedin-icon.svg" />
        </div>
        <div class="text-wrapper">
          <a href='https://figmaland.com/' target="_blank">Designed by Figmaland</a>
          <p>Developed by Patryk Zabłocki</p>
        </div>
      </div>
    </div>
</template>

<script>
export default {
name: 'Footer',
}
</script>

<style lang='scss' scoped>
@import "../styles/colors.scss";

.footer {
    background: $color-secondary-blue;
    padding: 45px 0;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 30px;

  @media screen and (min-width: 768px) {
    flex-direction: row;
    justify-content: space-between;
  }
}

.socials-wrapper {
  display: flex;
  column-gap: 35px;
}

.text-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;

  a, p {
    font-family: 'Roboto', sans-serif;
    font-weight: 400;
    font-size: 13px;
    line-height: 23px;
    letter-spacing: 0.1px;
    color: $color-light-text;
    text-decoration: none;
  }

  @media screen and (min-width: 768px) {
    align-items: flex-start;
    justify-content: flex-end;
  }
}
</style>