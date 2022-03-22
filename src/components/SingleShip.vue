<template>
<p>name: {{ship.name}}</p>
</template>

<script>

export default {
  name: 'SingleShip',
  props: {
    ship: {
      type: Object,
      default: () => {},
    },
  },
  setup() {
    return { };
  },
};
</script>

<style lang="scss">

</style>
