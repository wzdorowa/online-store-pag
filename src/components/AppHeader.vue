<template>
  <div class="header">
    <span class="header__logo">LOGO</span>
    <div class="header__user-info">
      <a class="header__link" href="/">
        <img class="header__icon" src="@/components/icons/person.svg" alt="bag" width="24px" height="24px">
      </a>
      <a class="header__link" href="/">
        <img class="header__icon" src="@/components/icons/favorite.svg" alt="bag" width="24px" height="24px">
      </a>
      <a class="header__link" href="/">
        <img class="header__icon" src="@/components/icons/bag.svg" alt="bag" width="24px" height="24px">
      </a>
      <a class="header__link" href="/">
        <img class="header__icon" src="@/components/icons/menu.svg" alt="bag" width="24px" height="24px">
      </a>
    </div>

  </div>
</template>

<style lang="scss" scoped>
  .header {
    display: flex;
    justify-content: space-between;
    padding: 22px 24px 30px 20px;

    &__logo {
      font-weight: 700;
      font-size: 22px;
      line-height: 16px;
      letter-spacing: 0.04em;
      color: #000;
    }

    &__user-info {
      display: flex;
      justify-content: space-between;
      min-width: 160px;
    }

    &__icon {
      display: block;
      width: 16px;
      height: 16px;
    }
  }
</style>