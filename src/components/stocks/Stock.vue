<template>
  <div class="col-md-4 col-sm-6">
    <div class="panel panel-success">
      <div class="panel-heading">
        <h3 class="panel-title">
          {{ stock.name }}
          <!-- 상위 컴포넌트로 부터 전달 받은 props 데이타 -->
          <small>(Price: {{ stock.price }} )</small>
        </h3>
      </div>
      <div class="panel-body">
        <div class="pull-left">
          <input type="number" class="form-control" placeholder="Quantity" v-model.number="quantity">
        </div>
        <div class="pull-right">
          <button class="btn btn-success" @click="buyStock" :disabled="quantity <= 0 || !Number.isInteger(quantity)">Buy</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['stock'],

  data() {
    return {
      quantity: 0
    }
  },
  methods: {
    buyStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity,
      };
      console.log(order);
      this.quantity = 0;
    }
  }
}
</script>