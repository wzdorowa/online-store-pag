<template>
  <AppHeader />
  <AppProduct
    v-bind:product="product"
  />
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppProduct from '@/components/AppProduct.vue'

export default {
  name: 'App',
  data() {
    return {
      product: {
        name: 'Пижама для девочек',
        article: '02765/46',
        images: [
          { id: 0, src: '/slider-images/product-view1.jpeg' },
          { id: 1, src: '/slider-images/product-view2.jpeg' },
          { id: 2, src: '/slider-images/product-view3.jpeg' },
          { id: 3, src: '/slider-images/product-view4.jpeg' },
          { id: 4, src: '/slider-images/product-view5.jpeg' },
        ],
        reviews: {
          rating: 4,
          numberReviews: 14
        },
        price: {
          base: 1500,
          discountPrice: 800,
          tags: ['скидка - 36%', 'акция - 20%']
        },
        sizes: ['80-86', '86-92', '92-98', '98-104', '104-110']
      }
    }
  },
  components: {
    AppHeader, AppProduct
  }
}
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Open Sans', Arial, Helvetica, sans-serif;
  font-size: 14px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333333;
}
</style>
