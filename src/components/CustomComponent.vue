<template>
<SimpleButton text="login" @click="isModalVisible = true"/>
  <teleport to="#modal">
  <TestModal v-if="isModalVisible"/>
  </teleport>
  <SiteFooter/>
</template>

<script>

import SiteFooter from '@/components/SiteFooter.vue';
import SimpleButton from '@/components/SimpleButton.vue';
import TestModal from '@/components/TestModal.vue';
import { ref } from 'vue';

export default {
  name: 'CustomComponent',
  components: {
    SimpleButton,
    SiteFooter,
    TestModal,
  },
  setup() {
    const isModalVisible = ref(false);

    return { isModalVisible };
  },
};
</script>

<style lang="scss">

</style>
