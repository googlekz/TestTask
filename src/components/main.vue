<template>
  <div class="table">
    <left
      v-model="isSort"
      @filter="filterArr"
      @sort="sortArr"
    />
    <center-block
      class="center"
      @change="(val) => this.resultArr = val"
      :my-arr="isSort ? sortArr : currentArray"/>
    <right
      :result-arr="resultArr"
    />
  </div>
</template>

<script>
import Left from './left'
import Right from './right'
import CenterBlock from './center'

export default {
  name: 'main',
  components: {CenterBlock, Right, Left},
  data: () => ({
    currentArray: [],
    myArr: [],
    isSort: false,
    resultArr: []
  }),
  created () {
    this.makeArr()
  },
  computed: {
    sortArr () {
      return [...this.currentArray].sort((item, item2) => {
        return item2.amount - item.amount
      })
    }
  },
  methods: {
    filterArr (radioValue) {
      this.currentArray = []
      switch (radioValue) {
        case 'all':
          this.currentArray = this.myArr
          break
        case 'less':
          this.myArr.forEach((item) => {
            return item.amount < 0 ? this.currentArray.push(item) : ''
          })
          break
        case 'more':
          this.myArr.forEach((item) => {
            return item.amount >= 0 ? this.currentArray.push(item) : ''
          })
          break
      }
    },
    makeArr () {
      for (let i = 0; i < 100; i++) {
        this.myArr.push({
          id: i,
          amount: this.fillArray()
        })
      }
      this.currentArray = this.myArr
    },
    fillArray () {
      return Math.floor(Math.random() * (1000 - -1000) + -1000)
    }
  }
}
</script>

<style scoped lang="scss">
.table {
  max-width: 1080px;
  margin: auto;
  border: 1px solid #a5a5a5;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  justify-content: space-between;

  & > div {
    padding: 0 20px;
  }

  & .center {
    border-color: #a5a5a5;
    border-style: solid;
    border-width: 0 1px 0 1px;
  }
}
</style>
