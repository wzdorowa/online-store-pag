<template lang="pug">
.like-button
    label.like-button__filter
      input.like-button__content(
        type='checkbox',
        v-bind:name="name",
        v-bind:checked="checked"
      )
      span.like-button__indicator
</template>

<script>
export default {
  props: ['checked', 'name']
}
</script>

<style lang="scss" scoped>
  .like-button {
    width: 44px;
    height: 44px;
    background-color: #333333;

    &__filter {
      position: relative;
      cursor: pointer;
    }

    &__content {
      opacity: 0;
    }

    &__indicator {
      position: absolute;
    }

    &__filter input[type='checkbox']:checked {
      & ~ .like-button__indicator {
        &::before {
          position: absolute;
          top: 14.5px;
          left: 0;
          right: 0;
          margin: auto;
          width: 15px;
          height: 15px;
          fill: #fff;
          content: url('@/components/icons/favorite-white.svg');
        }
      }
    }

    &__filter input[type='checkbox']:not(:checked) {
      & ~ .like-button__indicator {
        &::before {
          position: absolute;
          top: 14.5px;
          left: 0;
          right: 0;
          margin: auto;
          width: 15px;
          height: 15px;
          content: url('@/components/icons/favorite-white-border.svg');
        }
      }
    }
  }
</style>