<template>
  <div v-if="error">{{error}}</div>
  <suspense v-else>
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
import { onErrorCaptured, ref } from 'vue';
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
  setup() {
    const error = ref(null);

    onErrorCaptured((e) => {
      error.value = e;
    });

    return {
      error,
    };
  },
};
</script>
