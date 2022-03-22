<template>
<button @click="addItem">add</button>
</template>

<script>

export default {
  name: 'SimpleButton',
  setup(props, { emit }) {
    function addItem() {
      emit('addItem');
    }
    return { addItem };
  },
};
</script>

<style lang="scss">

</style>
