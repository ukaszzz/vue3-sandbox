<template>
<BaseInput name="input" v-model:firstName="firstName" v-model:lastName="lastName"/>
  <p>{{lastName}}</p>
  <p>{{firstName}}</p>
  <button class="button" @click="revertText">revert Text</button>
</template>

<script>

import BaseInput from '@/components/BaseInput.vue';
import { ref } from 'vue';

export default {
  name: 'CustomComponent',
  components: {
    BaseInput,
  },
  setup() {
    const firstName = ref('');
    const lastName = ref('');

    function revertText() {
      firstName.value = firstName.value.split('').reverse().join('');
      lastName.value = lastName.value.split('').reverse().join('');
      return lastName.value;
    }

    return {
      revertText,
      firstName,
      lastName,
    };
  },
};
</script>

<style lang="scss">

</style>
