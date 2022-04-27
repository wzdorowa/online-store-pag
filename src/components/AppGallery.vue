<template lang="pug">
.gallery
  figure.gallery__item(
    v-for="image in images"
    v-bind:class="'gallery__item_' + image.id")
    img.gallery__img(
      v-bind:src="image.src"
      v-bind:alt="image.name"
      v-bind:aria-label="image.name")
    .gallery__info
      .gallery__icon-container
        img.gallery__icon-full-screen(src="@/components/icons/full-screen.svg" alt="full-screen" width="16px" height="16px")
      a.gallery__link(v-bind:href="image.href")
        img.gallery__icon-bag(src="@/components/icons/bag-white.svg" alt="bag" width="32px" height="34px")
        span.gallery__text Узнай, что на мне
      .gallery__favorite
        img.gallery__icon-favorite(src="@/components/icons/favorite-white.svg" alt="favorite" width="15px" height="15.5px")
        span.gallery__number-favorite {{image.numberFavorite}}
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
      width: 100%;

      &:hover {
        & > .gallery__info {
          display: flex;
        }
      }

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

    &__info {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      padding: 16px 16px 20.5px 16px;
      background-color: #333333;
      opacity: 0.7;
    }

    &__icon-container {
      display: flex;
      justify-content: flex-end;
      width: 100%;
    }

    &__icon-full-screen {
      width: 16px;
      height: 16px;
      cursor: pointer;
    }

    &__link {
      display: flex;
      flex-direction: column;
      align-items: center;
      cursor: pointer;
    }

    &__icon-bag {
      display: block;
      width: 32px;
      height: 34px;
    }

    &__text {
      margin-top: 7px;
      color: #fff;
    }

    &__favorite {
      display: flex;
      align-items: center;
    }

    &__icon-favorite {
      display: inline-block;
      width: 15px;
      height: 15.5px;
      margin-right: 6.5px;
    }

    &__number-favorite {
      display: inline-block;
      color: #fff;
    }
  }
</style>