<template>
  <div v-if="errors">errrrrrrrr</div>
  <Suspense>
    <template #default> <StarShipsList />
    </template>
    <template #fallback>
      <AppLoader/>
    </template>
  </Suspense>
</template>

<script>

import StarShipsList from '@/components/StarShipsList.vue';
import AppLoader from '@/components/AppLoader.vue';
import { onErrorCaptured, ref } from 'vue';

export default {
  name: 'CustomComponent',
  components: {
    StarShipsList,
    AppLoader,
  },
  setup() {
    const errors = ref(null);

    onErrorCaptured((e) => {
      errors.value = e;
      return true;
    });
    return { errors };
  },
};
</script>

<style lang="scss">

</style>
