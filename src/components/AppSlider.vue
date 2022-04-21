<template>
  <div class="slider">
    <div class="slider__image-container"
      v-for="image in images"
      v-bind:key="image.src"
    >
      <img
        v-if="image.id === currentSlideIndex"
        v-bind:src="image.src"
        v-bind:alt="image.productName"
        v-bind:aria-label="image.productName"
        class="slider__image">
    </div>
    <div class="slider__images-mini">
      <img class="slider__image-mini"
      v-for="image in images"
      v-bind:key="image.src"
      v-bind:src="image.src"
      v-bind:alt="image.productName"
      @click="setActiveSlide(image.id)">
    </div>
  </div>
    
</template>

<script>

export default {
  props: ['images'],
  data() {
    return {
      currentSlideIndex: 0,
    }
  },
  methods: {
    setActiveSlide(id) {
      this.currentSlideIndex = id;
    }
  }
}
</script>

<style lang="scss" scoped>
  .slider {
    position: relative;

    &__image {
      width: 100%;
      height: 100%;
      display: block;
    }

    &__images-mini {
      position: absolute;
      top: 29px;
      left: 24px;
    }

    &__image-mini {
      display: block;
      width: 40px;
      height: 52px;
      margin-bottom: 4px;
    }
  }
</style>