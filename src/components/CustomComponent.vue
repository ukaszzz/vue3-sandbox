<template>
<h1>{{price}}</h1>
  <button @click="addOrder">add order</button>
  <p>quantity: {{quantity}}</p>
  <p>price: {{price}}</p>
  <p>totPrice: {{totPrice}}</p>
  <p>tax: {{tax}}</p>
</template>

<script>
import { reactive, toRefs } from 'vue';

export default {
  name: 'CustomComponent',
  setup() {
    const state = reactive({
      quantity: 0,
      price: 100,
      totPrice: 0,
      tax: 0,
    });

    function addOrder() {
      state.quantity += 1;
      state.totPrice = state.quantity * state.price;
      state.tax = state.totPrice * 0.23;
    }

    return {
      addOrder,
      ...toRefs(state),
    };
  },

};
</script>
