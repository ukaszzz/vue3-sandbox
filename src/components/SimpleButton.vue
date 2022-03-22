<template>
<button>{{text}}</button>
</template>

<script>

export default {
  name: 'SimpleButton',
  props: {
    text: {
      type: String,
      default: 'cos',
    },
  },
  setup() {
    return { };
  },
};
</script>

<style lang="scss">

</style>
