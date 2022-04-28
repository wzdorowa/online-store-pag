<template lang="pug">
.content
  AppHeader
  .content__main
    .content__product
      AppProduct(v-bind:product="product")
    .content__gallery
      AppGallery(:images="gallery")
  AppFooter(v-bind:navigation="navigation")
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppProduct from '@/components/AppProduct.vue'
import AppGallery from '@/components/AppGallery.vue'
import AppFooter from '@/components/AppFooter.vue'

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
        sizes: ['80-86', '86-92', '92-98', '98-104', '104-110'],
      },
      gallery: [
        { id: 1, src: '/gallery/style-1.jpg', name: 'style 1', numberFavorite: 350, href: '/' },
        { id: 2, src: '/gallery/style-2.jpg', name: 'style 1', numberFavorite: 32, href: '/' },
        { id: 3, src: '/gallery/style-3.jpg', name: 'style 1', numberFavorite: 146, href: '/' },
        { id: 4, src: '/gallery/style-4.jpg', name: 'style 1', numberFavorite: 200, href: '/' },
        { id: 5, src: '/gallery/style-5.jpg', name: 'style 1', numberFavorite: 279, href: '/' },
      ],
      navigation: [
        {
          sectionName: 'Покупателям',
          links: [
            { name: 'Каталог', href: '/' },
            { name: 'Акции', href: '/' },
            { name: 'Бренды', href: '/' }
          ]
        },
        {
          sectionName: 'О нас',
          links: [
            { name: 'О компании', href: '/' },
            { name: 'Новости', href: '/' },
            { name: 'Команда', href: '/' }
          ]
        }
      ],
    }
  },
  components: {
    AppHeader,
    AppProduct,
    AppGallery,
    AppFooter
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Open Sans', Arial, Helvetica, 'PT Sans', sans-serif;
  font-size: 14px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333333;
}

.content {
  &__gallery {
    margin-top: 40px;
  }
}
</style>
