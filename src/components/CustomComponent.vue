<template>
<SimpleButton @add-item="increaseCount"/>
<BaseNotification :notification="notificationText" @hide-notification="hideNotification"/>
</template>

<script>

import BaseNotification from '@/components/BaseNotification.vue';
import SimpleButton from '@/components/SimpleButton.vue';
import { computed, ref } from 'vue';

export default {
  name: 'CustomComponent',
  components: {
    SimpleButton,
    BaseNotification,
  },
  setup() {
    const number = ref(0);

    const notificationText = computed(() => `number of item in card ${number.value}`);

    function increaseCount() {
      number.value += 1;
      console.log(number.value);
    }

    function hideNotification() {
      console.log('hide');
    }
    return { increaseCount, notificationText, hideNotification };
  },
};
</script>

<style lang="scss">

</style>
