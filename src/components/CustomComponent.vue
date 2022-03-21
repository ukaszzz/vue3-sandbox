<template>
<p>{{pension}}</p>
  <button @click="pensionIncrement">increment</button>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'HelloWorld',
  setup() {
    const pension = ref(100);

    function pensionIncrement() {
      pension.value += 1;
    }
    return {
      pension,
      pensionIncrement,
    };
  },

};
</script>
