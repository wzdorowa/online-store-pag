<template lang="pug">
.dropdown
  input.dropdown__input(
    v-bind:name="name"
    v-bind:placeholder="placeholder"
    v-bind:value="value"
    type='text'
    readonly='readonly'
    @click="handleClickInput()"
  )
  span.dropdown__arrow-down(@click="handleClickInput()")
  .dropdown__rows(v-bind:class="{ dropdown__rows_opened: isOpen}")
    .dropdown__row(
      v-for="(value, index) in dropdownValues"
      @click="handleClickDropdownRow(index)"
    )
      span {{value}}
</template>

<script>
export default {
  props: ['placeholder', 'name', 'dropdownValues'],
  methods: {
    handleClickInput() {
      this.isOpen = !this.isOpen;
    },

    handleClickDropdownRow(id) {
      this.value = this.dropdownValues[id];
      this.isOpen = !this.isOpen;
    }
  },
  data() {
    return {
      value: null,
      isOpen: false,
    }
  }
}
</script>

<style lang="scss">
  .dropdown {
    position: relative;
    width: 315px;
    cursor: pointer;

    &__input {
      position: relative;
      width: 100%;
      font-family: inherit;
      font-size: 14px;
      line-height: 20px;
      letter-spacing: 0.5px;
      padding: 11px 15px;
      border: 1px solid #333333;
      cursor: pointer;

      &::placeholder {
        color: #333333;
      }
    }

    &__arrow-down {
      position: relative;

      &::before {
        position: absolute;
        content: '';
        right: 15px;
        top: 0;
        width: 10.5px;
        height: 10.5px;
        border-top: 1px solid #333333;
        border-right: 1px solid #333333;
        transform: rotate(135deg);
      }
    }

    &__rows {
      display: none;

      &_opened {
        display: block;
      }
    }

    &__row {
      width: 100%;
      padding: 16px 20px;
      border: 1px solid #333333;
      border-top: none;

      &:hover {
        background-color: rgba($color: #333333, $alpha: 0.1);
      }
    }
  }
</style>