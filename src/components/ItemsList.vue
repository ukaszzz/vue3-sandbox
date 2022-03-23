<template>
<section>
  <router-link v-for="(item, index) in items" :key="index"
               :to="{name: 'Item', params: {id:index+1}}">
  <SingleItem :item="item"/>
  </router-link>
</section>
</template>

<script>
import SingleItem from '@/components/SingleItem.vue';
import { ref } from 'vue';

export default {
  name: 'ItemsList',
  components: {
    SingleItem,
  },

  async setup() {
    const items = ref(null);
    const respone = await fetch('https://swapi.dev/api/people');
    const parsedResponse = await respone.json();

    items.value = [...parsedResponse.results];
    console.log();

    return {
      items,
    };
  },
};

</script>

<style lang="scss">

</style>
