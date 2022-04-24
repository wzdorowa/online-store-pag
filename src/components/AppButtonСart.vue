<template lang="pug">
button.button-cart {{value}}
</template>

<script>
export default {
  props: ['value']
}
</script>

<style lang="scss" scoped>
  .button-cart {
    font-family: inherit;
    font-size: inherit;
    letter-spacing: 0.5px;
    color: #FFFFFF;
    padding: 12px 28px;
    background-color: #333333;
    border: none;
    cursor: pointer;
  }
</style>