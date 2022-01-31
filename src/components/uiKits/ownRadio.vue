<template>
  <div class="input-wrap">
    <label class="cursor-pointer" :for="radioValue">
      <input
        class="cursor-pointer"
        type="radio"
        :id="radioValue"
        :name="radioName"
        :value="radioValue"
        @change="$emit('change', $event.target.value)"
        :checked="isChecked"
      >
      <span>{{ labelText }}</span>
    </label>
  </div>
</template>

<script>
export default {
  name: 'ownRadio',
  model: {
    prop: 'modelValue',
    event: 'change'
  },
  props: {
    modelValue: {
      default: ''
    },
    radioValue: {
      type: [String, null]
    },
    radioName: {
      type: String
    },
    labelText: {
      type: String
    }
  },
  computed: {
    isChecked () {
      return this.modelValue === this.radioValue
    }
  }
}
</script>

<style scoped>
</style>
