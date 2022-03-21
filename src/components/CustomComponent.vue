<template>
<div>
  <p>shares: {{shares}}</p>
  <p>price: {{sharesPrice}}</p>
  <p>total: {{sharesTotal}}</p>
  <button @click="changeSharesNumber(1)">buy 1</button>
  <button @click="changeSharesNumber(5)">buy 5</button>
  <button @click="changeSharesNumber(-1)">sell 1</button>
  <button @click="changeSharesNumber(-5)">sell 5</button>
</div>
</template>

<script>
import { ref, computed, watch } from 'vue';

export default {
  name: 'CustomComponent',
  setup() {
    const shares = ref(15);
    const sharesPrice = ref(20);
    const sharesTotal = computed(() => shares.value * sharesPrice.value);

    function changeSharesNumber(number) {
      shares.value += number;
    }
    function changePrice(min, max) {
      const priceDiff = Math.floor(Math.random() * (max - min) + min);
      console.log(priceDiff);
      sharesPrice.value += priceDiff;
      console.log(sharesPrice.value);
    }

    watch(shares, (prevSharesNumber, nextSharesNumber) => {
      const newPrice = prevSharesNumber > nextSharesNumber
        ? changePrice(1, 5) : changePrice(-1, -5);
      console.log(newPrice);
    });

    return {
      shares,
      sharesPrice,
      sharesTotal,
      changeSharesNumber,
    };
  },

};
</script>
