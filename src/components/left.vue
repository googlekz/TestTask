<template>
  <div class="left-block">
    <h4 class="main-title">Левая</h4>
    <div class="content">
      <div class="content-radio">
        <div class="filter">
          <p class="filter__title">Фильтрация</p>
          <own-radio
            class="filter__item"
            v-model="radioValueEmit"
            radio-value="all"
            radio-name="filter"
            label-text="Все"
          ></own-radio>
          <own-radio
            class="filter__item"
            v-model="radioValueEmit"
            radio-value="less"
            radio-name="filter"
            label-text="amount меньше 0"
          ></own-radio>
          <own-radio
            class="filter__item"
            v-model="radioValueEmit"
            radio-value="more"
            radio-name="filter"
            label-text="amount больше 0"
          ></own-radio>
        </div>
      </div>
      <div class="content-checkbox">
        <label for="is-sort" class="cursor-pointer">
          <input v-model="vModel" type="checkbox" id="is-sort" class="cursor-pointer" name="is-sort">
          <span>Сортировать</span>
        </label>
      </div>
    </div>
  </div>
</template>

<script>
import OwnRadio from './uiKits/ownRadio'

export default {
  name: 'leftBlock',
  components: {OwnRadio},
  model: {
    prop: 'statevalue',
    event: 'change'
  },
  data: () => ({
    radioValue: 'all'
  }),
  props: {
    stateValue: {
      type: Boolean
    }
  },
  computed: {
    radioValueEmit: {
      get () {
        return this.radioValue
      },
      set (val) {
        this.radioValue = val
        this.$emit('filter', val)
      }
    },
    vModel: {
      get () {
        return this.stateValue
      },
      set (val) {
        this.$emit('change', val)
      }
    }
  }
}
</script>

<style scoped lang="scss">
.left-block {
  & .filter {
    margin-bottom: 30px;

    &__title {
      margin-bottom: 5px;
      font-style: italic;
      color: #707070;
    }

    &__title, &__item {
      text-align: left;
    }
  }

  & .content-checkbox {
    text-align: left;
  }
}
</style>
