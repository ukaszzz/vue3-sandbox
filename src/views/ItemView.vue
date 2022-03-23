<template>
  <suspense>
    <template #default>
      <ItemDetails :id="id"/>
    </template>
    <template #fallback>
      <BaseLoader/>
    </template>
  </suspense>
</template>

<script>
// @ is an alias to /src

import BaseLoader from '@/components/BaseLoader.vue';
import ItemDetails from '@/components/ItemDetails.vue';

export default {
  name: 'HomeView',
  components: {
    ItemDetails,
    BaseLoader,
  },
  props: {
    id: {
      typ: String,
    },
  },

};
</script>
