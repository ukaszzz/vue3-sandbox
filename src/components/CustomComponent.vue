<template>
  <ButtonComponent :text="'cos'">
    <template #image>
      <img src="public/favicon.ico" alt="sss"/>
    </template>
    <template #text>
     <p>test Text</p>
    </template>
  </ButtonComponent>
</template>

<script>

import ButtonComponent from '@/components/ButtonComponent.vue';

export default {
  name: 'CustomComponent',
  components: {
    ButtonComponent,
  },
  setup() {
    return { };
  },
};
</script>

<style lang="scss">

</style>
