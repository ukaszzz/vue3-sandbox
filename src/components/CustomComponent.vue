<template>
<h1>{{price}}</h1>
  <button @click="addOrder">add order</button>
  <p>quantity: {{quantity}}</p>
  <p>price: {{price}}</p>
  <p>totPrice: {{totPrice}}</p>
  <p>tax: {{tax}}</p>
</template>

<script>
import { ref, computed } from 'vue';

export default {
  name: 'CustomComponent',
  setup() {
    const quantity = ref(0);
    const price = ref(100);
    const totPrice = computed(() => price.value * quantity.value);
    const tax = computed(() => totPrice.value * 0.23);

    function addOrder() {
      quantity.value += 1;
    }
    return {
      addOrder,
      quantity,
      price,
      totPrice,
      tax,
    };
  },

};
</script>
