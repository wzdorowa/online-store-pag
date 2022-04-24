<template lang="pug">
.reviews
  .reviews__rating
    AppRating(v-bind:ratingStar="reviews.rating")
  span.reviews__text {{reviews.numberReviews}} {{this.convertNumToWordform(reviews.numberReviews, wordForms)}}
  AppArrowLink(v-bind:link="'/'")
</template>

<script>
import AppRating from '@/components/AppRating.vue'
import AppArrowLink from '@/components/AppArrowLink.vue'

export default {
  props: ['reviews'],
  components: {
    AppRating, AppArrowLink
  },
  data() {
    return {
      wordForms: ['отзыв', 'отзыва', 'отзывов']
    }
  },

  methods: {
    convertNumToWordform(amount, textForms) {
      const [one, two, many] = textForms;

      const isMatchingValue = amount => Number(amount) > 1 && Number(amount) < 5;

      if (String(amount).includes('1')) {
        if (amount === 1) {
          return one;
        }
        if (String(amount)[1] === '1' && amount !== 11) {
          return one;
        }
      } else if (String(amount).length === 1 && isMatchingValue(amount)) {
        return two;
      } else if (String(amount).length > 1 && isMatchingValue(String(amount)[1])) {
        return two;
      }
      return many;
    }
  }
}
</script>

<style lang="scss" scoped>
  .reviews {
    display: flex;
    align-items: center;

    &__rating {
      margin-right: 5px;
    }

    &__text {
      margin-right: 8px;
    }
  }
</style>