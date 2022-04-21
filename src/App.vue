<template>
  <AppHeader />
  <AppSlider
    v-bind:images="sliderImages"
  />
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppSlider from '@/components/AppSlider.vue'

export default {
  name: 'App',
  data() {
    return {
      sliderImages: [
        { id: 0, src: '/slider-images/product-view1.jpeg', productName: 'Пижама для девочек' },
        { id: 1, src: '/slider-images/product-view2.jpeg', productName: 'Пижама для девочек' },
        { id: 2, src: '/slider-images/product-view3.jpeg', productName: 'Пижама для девочек' },
        { id: 3, src: '/slider-images/product-view4.jpeg', productName: 'Пижама для девочек' },
        { id: 4, src: '/slider-images/product-view5.jpeg', productName: 'Пижама для девочек' },
      ]
    }
  },
  components: {
    AppHeader, AppSlider
  }
}
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}
</style>
