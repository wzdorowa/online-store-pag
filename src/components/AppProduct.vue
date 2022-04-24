<template>
  <div class="product">
    <AppSlider
      v-bind:images="product.images"
      v-bind:name="product.name"
    />
    <div class="product__content">
      <h1 class="product__title">{{product.name}}</h1>
      <span class="product__article">Арт. {{product.article}}</span>
      <div class="product__reviews">
        <span class="product__reviews-text">Oтзывы</span>
          <AppReviews
            v-bind:reviews="product.reviews"
          />
      </div>
      <div class="product__price">
        <AppPrice
          v-bind:price="product.price"
        />
      </div>
      <div class="product__dropdown">
        <AppDropdown
          v-bind:placeholder="'Выбрать размер'"
          v-bind:dropdownValues="product.sizes"
        />
      </div>
      <div class="product__size-grid">
        <a class="product__size-grid-link" href="/">Определить размер</a>
      </div>
      <div class="product__counter">
        <AppCounter/>
      </div>
    </div>
  </div>

</template>

<script>
import AppSlider from '@/components/AppSlider.vue'
import AppReviews from '@/components/AppReviews.vue'
import AppPrice from '@/components/AppPrice.vue'
import AppDropdown from '@/components/AppDropdown.vue'
import AppCounter from '@/components/AppCounter.vue'

export default {
  props: ['product'],
  components: {
    AppSlider, AppReviews, AppPrice, AppDropdown, AppCounter
  }
}
</script>

<style lang="scss" scoped>
  .product {
    &__content {
      padding: 20px;
    }

    &__title {
      font-weight: 600;
      font-size: 18px;
    }

    &__article {
      font-size: 12px;
      color: #828282;
    }

    &__reviews {
      display: flex;
      font-size: 14px;
    }

    &__reviews-text {
      margin-right: 13px;
    }

    &__dropdown {
    }

    &__size-grid {

    }

    &__size-grid-link {
      &:visited {
        color: #333333;
      }
    }
  }
</style>
