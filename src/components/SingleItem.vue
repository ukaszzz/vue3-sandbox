<template>
<section>
  <p>{{item.name}}</p>
</section>
</template>

<script>

export default {
  name: 'SingleItem',
  props: {
    item: {
      type: Object,
      require: true,
    },
  },
};

</script>

<style lang="scss">

</style>
