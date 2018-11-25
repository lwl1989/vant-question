<template>
  <van-popup v-model="show_popup">
    <div style="padding: 1em 1em 1em 1em;">
      <template v-if="money > 0">
        <p>恭喜你，您的额度为</p>
        <h3 style="color: red"> {{money}} 万元!</h3>
      </template>
      <template v-else>
        <p>您还没有获得额度哦！请再接再接！</p>
      </template>
    </div>
  </van-popup>
</template>

<script>
export default {
  name: 'Result',
  data: function () {
    return {
      in_mall: '1',
      years: '1',
      local_people: '1',
      living: '1',
      age: '1',
      sales: '1',
      money: 1,
      card: '1',
      show_popup: false,
      money_show: ''
    }
  },
  methods: {
    show: function (obj) {
      this.show_popup = true
      this.in_mall = obj.in_mall
      this.years = obj.years
      this.living = obj.living
      this.age = obj.age
      this.sales = obj.sales
      this.card = obj.card
      this.local_people = obj.local_people
      this.money = 1
      if (this.in_mall === '1') {
        this.money *= parseInt(this.in_mall)
      } else {
        this.money = 0
      }

      if (this.money !== 0) {
        this.cal()
      }
    },
    cal: function () {
      this.cal_years()
      this.cal_age()
      this.cal_card()
      this.cal_living()
      this.cal_local_people()
      this.cal_sales()
      if (this.money > 100) {
        this.money = 100
      } else {
        this.money = this.money - this.money % 5
      }
    },
    cal_years: function () {
      switch (this.years) {
        case '1':
          this.money *= 1.5
          break
        case '2':
          this.money *= 1
          break
        case '3':
          this.money *= 0.8
          break
        case '4':
          this.money *= 0.5
          break
        default:
          this.money = 0
      }
    },
    cal_local_people: function () {
      switch (this.local_people) {
        case '1':
          this.money *= 1
          break
        case '2':
          this.money *= 0.9
          break
        case '3':
          this.money *= 0.8
          break
        case '4':
        default:
          this.money *= 0.3
          break
      }
    },
    cal_living: function () {
      switch (this.living) {
        case '1':
          this.money *= 1.5
          break
        case '2':
          this.money *= 1
          break
        case '3':
          this.money *= 0.5
          break
        case '4':
        default:
          this.money *= 0.5
          break
      }
    },
    cal_card: function () {
      switch (this.card) {
        case '1':
        case '3':
          this.money *= 1
          break
        case '2':
          this.money *= 1.5
          break
        case '4':
          this.money *= 0.7
          break
        default:
          this.money = 0.5
      }
    },
    cal_age: function () {
      switch (this.age) {
        case '1':
        case '4':
          this.money *= 0.6
          break
        case '2':
        case '3':
          this.money *= 1
          break
        default:
          this.money *= 0
          break
      }
    },
    cal_sales: function () {
      switch (this.sales) {
        case '1':
          this.money *= 100
          break
        case '2':
          this.money *= 70
          break
        case '3':
          this.money *= 40
          break
        case '4':
          this.money *= 20
          break
        default:
          this.money = 0
      }
    }
  }
}
</script>

<style scoped>

</style>
