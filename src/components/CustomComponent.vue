<template>
  <div>{{count}}</div>
  <button @click="increment">increment</button>
  <ChildComponent v-if="count <3"/>
</template>

<script>
import {
  onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted, ref,
} from 'vue';
import ChildComponent from '@/components/ChildComponent.vue';

export default {
  name: 'CustomComponent',
  components: {
    ChildComponent,
  },
  setup() {
    const count = ref(0);

    function increment() {
      count.value += 1;
    }
    console.log('setup');

    onBeforeMount(() => {
      console.log('onBeforeMount');
    });
    onMounted(() => {
      console.log('onMounted');
    });
    onBeforeUpdate(() => {
      console.log('onBeforeUpdate');
    });
    onUpdated(() => {
      console.log('onUpdated');
    });
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount');
    });
    onUnmounted(() => {
      console.log('onUnmounted');
    });
    return { count, increment };
  },
};
</script>

<style lang="scss">

</style>
