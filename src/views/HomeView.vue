<template>
  <div v-if="error">{{error}}</div>
  <suspense v-else>
    <template #default>
      <ItemsList/>
    </template>
    <template #fallback>
      <BaseLoader/>
    </template>
    </suspense>
</template>

<script>
// @ is an alias to /src

import BaseLoader from '@/components/BaseLoader.vue';
import ItemsList from '@/components/ItemsList.vue';
import { onErrorCaptured, ref } from 'vue';

export default {
  name: 'HomeView',
  components: {
    ItemsList,
    BaseLoader,
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
