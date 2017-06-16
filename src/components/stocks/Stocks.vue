<template>
  <div>
    <app-stock v-for="stock in stocks" :propStock="stock"></app-stock>
  </div>
</template>
<script>
import Stock from './Stock.vue';
export default {
  components: {
    appStock: Stock
  },
  computed: {
    stocks() {
      return this.$store.getters.stocks;  // getter로 현재 state 값을 가져옵니다.
    }
  }
}
</script>