<template lang="pug">
.footer
  .footer__navigation
    ul.footer__list(v-for="column in navigation")
      h2.footer__list-title {{column.sectionName}}
      li.footer__item-list(v-for="link in column.links")
        a.footer__item-link(v-bind:href="link.href") {{link.name}}
  .footer__subscribe
    h2.footer__subscribe-title Узнайте первыми о новинках и акциях
    .footer__subscribe-form
      input.footer__subscribe-input(placeholder="Адрес электронной почты")
      span.footer__subscribe-cancel
    button.footer__subscribe-button Подписаться
</template>

<script>
export default {
  props: ['navigation']
}
</script>

<style lang="scss">
  .footer {
    padding: 20px;

    &__navigation {
      display: grid;
      grid-template-columns: repeat(2, 51.2%);
      margin-top: 23px;
    }

    &__list {
      list-style: none;
      padding: 0;
    }

    &__list-title {
      font-size: 17px;
      font-weight: 400;
      text-transform: uppercase;
      margin-bottom: 16px;
    }

    &__item-list {
      margin-top: 9px;
    }

    &__item-link {
      letter-spacing: 0.04em;
      text-decoration: none;
      color: inherit;
    }

    &__subscribe {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      margin-top: 60px;
    }

    &__subscribe-title {
      max-width: 255px;
      margin-right: auto;
      font-size: 17px;
      font-weight: 400;
      text-transform: uppercase;
      margin-bottom: 20px;
    }

    &__subscribe-form {
      width: 100%;
      margin-bottom: 26px;
    }

    &__subscribe-input {
      width: 100%;
      padding: 13px 16px;
      border: none;
      border-bottom: 1px solid #C4C4C4;

      &::placeholder {
        font-size: 14px;
        letter-spacing: 0.07em;
        color: #828282;
      }
    }

    &__subscribe-cancel {
      position: relative;

      &::before {
        position: absolute;
        content: "";
        width: 11px;
        right: 10px;
        top: 10px;
        border-top: 1px solid #C4C4C4;
        transform: matrix(-0.71, -0.71, -0.71, 0.71, 0, 0);
      }

      &::after {
        position: absolute;
        content: "";
        width: 11px;
        right: 11px;
        top: 10px;
        border-top: 1px solid #C4C4C4;
        transform: rotate(-45deg);
      }
    }

    &__subscribe-button {
      font-size: inherit;
      color: inherit;
      letter-spacing: 0.04em;
      background: #FFFFFF;
      padding: 8px 28px;
      border: 1px solid #333333;
    }
  }
</style>