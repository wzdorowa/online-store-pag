<template lang="pug">
.counter
  button.counter__plus(@click="add()") +
  span.counter__value {{value}}
  button.counter__minus(@click="subtract()") –
</template>

<script>
export default {
  data() {
    return {
      value: 1
    }
  },
  methods: {
    add() {
      this.value += 1;
    },

    subtract() {
      if (this.value > 1) {
        this.value -= 1;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .counter {
    display: flex;

    &__minus,
    &__plus,
    &__value {
      width: 48px;
      height: 44px;
      border: none;
      font-family: inherit;
      background-color: #F2F2F2;
    }

    &__minus,
    &__plus {
      cursor: pointer;
    }

    &__value {
      display: inline-block;
      text-align: center;
      line-height: 44px;
    }
  }
</style>