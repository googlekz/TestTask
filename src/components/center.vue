<template>
  <div class="center-block">
    <h4 class="main-title">Центральная</h4>
    <div class="content">
      <label
        :for="`is-sort${index}`"
        class="arr-item cursor-pointer"
        v-for="(item, index) in myArr"
        :key="`item${index}`"
      >
        <input
          class="cursor-pointer"
          :id="`is-sort${index}`"
          :value="item"
          v-model="selectedCheckboxSend"
          type="checkbox"
          :name="`is-sort${index}`"
        >
        <span>ID: {{ item.id }}</span>
        <span>amount: {{ item.amount }}</span>
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: 'centerBlock',
  props: {
    myArr: {
      type: Array
    }
  },
  data: () => ({
    selectedCheckbox: []
  }),
  computed: {
    selectedCheckboxSend: {
      get () {
        return this.selectedCheckbox
      },
      set (val) {
        this.selectedCheckbox = val
        this.$emit('change', val)
      }
    }
  },
  created () {
    this.selectedCheckboxSend = this.myArr
  }
}
</script>

<style scoped lang="scss">
.center-block {
  & .arr-item {
    display: flex;
    justify-content: start;
    align-items: center;
    gap: 10px;
    border-bottom: 1px solid #d2f0ff;
    padding: 10px 0 15px;
  }
}
</style>
