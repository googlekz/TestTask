<template>
  <div class="right-block">
    <h4 class="main-title">Правая</h4>
    <table class="result">
      <tr>
        <th>ID</th>
        <th>Amount</th>
      </tr>
      <tr v-for="(item, index) in resultArr" :key="`result-item${index}`">
        <td>{{ item.id }}</td>
        <td>{{ item.amount }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'rightBlock',
  props: {
    resultArr: {
      type: Array
    }
  }
}
</script>

<style scoped lang="scss">
.right-block {
  & .result {
    width: 100%;
    border-collapse: collapse;
  }

  & table, & th, & td {
    border: 1px solid #d2f0ff;
  }

  & th {
    background: #d2fff1;;
  }

  & td {
    &:first-child {
      background: #fff9f9;;
    }
  }
}
</style>
