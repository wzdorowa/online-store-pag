<template lang="pug">
.gallery
  figure.gallery__item(
    v-for="image in images"
    v-bind:class="'gallery__item_' + image.id")
    img.gallery__img(
      v-bind:src="image.src"
      v-bind:alt="image.name"
      v-bind:aria-label="image.name")
</template>

<script>
export default {
  props: ['images']
}
</script>

<style lang="scss">
  .gallery {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(4, 183.5px);
    grid-gap: 8px;

    &__item {
      position: relative;

      &_1 {
        grid-column-start: 1;
        grid-column-end: 3;
        grid-row-start: 1;
        grid-row-end: 3;
      }
    }

    &__img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
</style>