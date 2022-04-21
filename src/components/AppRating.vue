<template lang="pug">
.rating
  .rating__item-wrapper(v-for="(item, index) in amountStar")
    .rating__item.rating__item_active(v-if="index < ratingStar")
    .rating__item(v-else)
</template>

<script>

export default {
  props: ['ratingStar'],
  data() {
    return {
      amountStar: [1, 2, 3, 4, 5],
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
  .rating {
    display: flex;
    width: 58px;
    justify-content: space-between;

    &__item {
      width: 10px;
      height: 10px;
      background-image: url('@/components/icons/star.svg');

      &_active {
        background-image: url('@/components/icons/star-active.svg');
      }
    }
  }
</style>