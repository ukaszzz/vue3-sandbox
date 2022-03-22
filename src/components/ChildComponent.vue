<template>
<p>child component</p>
</template>

<script>

import {
  onBeforeMount,
  onBeforeUnmount,
  onBeforeUpdate,
  onMounted,
  onUnmounted,
  onUpdated,
} from 'vue';

export default {
  name: 'ChildComponent',
  setup() {
    console.log('setup from child');
    onBeforeMount(() => {
      console.log('onBeforeMount from child');
    });
    onMounted(() => {
      console.log('onMounted from child');
    });
    onBeforeUpdate(() => {
      console.log('onBeforeUpdate from child');
    });
    onUpdated(() => {
      console.log('onUpdated from child');
    });
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount from child');
    });
    onUnmounted(() => {
      console.log('onUnmounted from child');
    });
    return { };
  },
};
</script>
