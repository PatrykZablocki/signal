<template>
    <button>
        <slot />
    </button>
</template>

<script>
export default {
name: "PrimaryButton",
}
</script>

<style lang="scss" scoped>
@import "../../styles/colors.scss";
$shadow: 0px 4px 31px rgba(0, 0, 0, 0.15);

button {
    cursor: pointer;
    font-family: 'Nunito Sans', sans-serif;
    font-weight: 400;
    background: $color-primary;
    border: none;
    color: $color-light-text;
    font-size: 18px;
    line-height: 24px;
    letter-spacing: 0.2px;
    border-radius: 50px;
    padding: 14px 46px;
    box-shadow: $shadow;
}

.white {
    background: $color-light-background;
    color: $color-primary;
}
</style>