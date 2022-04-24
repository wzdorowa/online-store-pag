<template lang="pug">
span.arrow-link(href=link)
</template>

<script>
export default {
  props: ['link']
}
</script>

<style lang="scss" scoped>
  .arrow-link {
      display: inline-block;
      width: 10.5px;
      height: 10.5px;
      border-top: 1px solid #333333;
      border-right: 1px solid #333333;
      transform: rotate(45deg);
      cursor: pointer;
    }
</style>