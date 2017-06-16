
<template>
  <div class="container">
    <app-header></app-header>
    <div class="row">
      <div class="col-md-12">
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
export default {
  components: {
    'appHeader': Header
  },
  created() {
    this.$store.dispatch('initStocks');  // store에 등록된 action을 사용합니다.
  }
}
</script>

<style>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css");
body {
  padding: 30px;
}
</style>
