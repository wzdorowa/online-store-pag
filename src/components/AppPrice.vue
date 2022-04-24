<template lang="pug">
.price
  .price__cost
    span.price__current-value(v-if="price.discountPrice !== undefined") {{formatCost(price.discountPrice)}} &#x20bd
    span.price__base.price__base_crossed-out(v-if="price.discountPrice !== undefined") {{formatCost(price.base)}} &#x20bd
    span.price__current-value(v-if="price.discountPrice === undefined") {{formatCost(price.base)}} &#x20bd
    AppArrowLink(v-bind:link="'/'")
  .price__tags(v-if="price.tags !== undefined")
    span.price__tag(v-for="tag in price.tags") {{tag}}
</template>

<script>
import AppArrowLink from '@/components/AppArrowLink.vue'

export default {
  props: ['price'],
  methods: {
    formatCost(cost) {
      const value = cost.toLocaleString('ru-RU')
      return value
    }
  },
  components: {
    AppArrowLink
  }
}
</script>

<style lang="scss" scoped>
  .price {
    &__cost {
      display: flex;
      align-items: center;
    }

    &__current-value {
      display: inline-block;
      font-weight: bold;
      font-size: 24px;
      line-height: 24px;
      letter-spacing: 1px;
      margin-right: 12px;
    }

    &__base {
      display: inline-block;
      line-height: 20px;
      letter-spacing: 0.5px;
      text-decoration: line-through;
      color: #828282;
      margin-right: 17px;
    }

    &__tags {
      margin-top: 14px;
    }

    &__tag {
      font-size: 12px;
      line-height: 16px;
      padding: 3px 7.5px 2px 7px;
      border: 1px solid #333333;
      margin-right: 9px;
      letter-spacing: 0.1px;
    }
  }
</style>