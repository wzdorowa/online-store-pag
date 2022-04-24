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
        <a class="product__link-content" href="/">Определить размер</a>
      </div>
      <div class="product__counter">
        <AppCounter/>
      </div>
      <div class="product__buttons">
        <AppButtonCart :value="'Добавить в корзину'"/>
        <AppLikeButton :checked="false" :name="'like button'"/>
      </div>
      <div class="product__purchase">
        <a class="product__link-content" href="/">Купить в 1 клик</a>
      </div>
      <hr class="product__separator">
      <div class="product__link">
        <img class="product__link-icon" src="@/components/icons/description.svg"/>
        <a class="product__link-content" href="/">Описание товара</a>
      </div>
      <div class="product__link">
        <img class="product__link-icon" src="@/components/icons/time.svg"/>
        <a class="product__link-content" href="/">Доставка и возврат</a>
      </div>
      <div class="product__link product__link_shifted">
        <img class="product__link-icon" src="@/components/icons/cash-card.svg"/>
        <a class="product__link-content" href="/">Способы оплаты</a>
      </div>
      <div class="product__all-styles">
        <a class="product__link-content" href="/">Посмотреть все стили</a>
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
import AppButtonCart from '@/components/AppButtonСart.vue'
import AppLikeButton from '@/components/AppLikeButton.vue'

export default {
  props: ['product'],
  components: {
    AppSlider,
    AppReviews,
    AppPrice,
    AppDropdown,
    AppCounter,
    AppButtonCart,
    AppLikeButton,
  }
}
</script>

<style lang="scss" scoped>
  .product {
    &__content {
      padding: 25px 20px 20px 20px;
    }

    &__title {
      font-weight: 600;
      font-size: 18px;
      letter-spacing: -0.5px;
    }

    &__article {
      display: inline-block;
      font-size: 12px;
      letter-spacing: 0.5px;
      color: #828282;
      margin-top: 8px;
    }

    &__reviews {
      display: flex;
      font-size: 14px;
      margin-top: 17px;
    }

    &__price {
      margin-top: 46px;
    }

    &__reviews-text {
      letter-spacing: 0.5px;
      margin-right: 13px;
    }

    &__dropdown {
      margin-top: 35px;
    }

    &__size-grid {
      margin-top: 12px;
    }

    &__link-content {
      display: inline-block;
      letter-spacing: 0.5px;

      &:visited {
        color: #333333;
      }
    }

    &__counter {
      margin-top: 41px;
    }

    &__buttons {
      display: flex;
      justify-content: space-between;
      width: 251px;
      margin-top: 15px;
    }

    &__purchase {
      margin-top: 21px;
    }

    &__separator {
      width: 100%;
      margin-top: 29px;
      margin-bottom: 22.5px;
      border-top: 0.5px solid #C4C4C4;
    }

    &__link {
      margin-top: 13px;
      display: flex;

      &_shifted {
        margin-left: 2px;
      }
    }

    &__link-icon {
      display: block;
      margin-right: 6.5px;
    }

    &__all-styles {
      display: flex;
      justify-content: space-around;
      margin-top: 58px;
    }
  }
</style>
