<template>
  <div
    class="single-item"
  >
    <p>Candidate {{ index + 1 }}</p>
    <p>Name: {{ item.firstName }} {{ item.lastName }}</p>
    <p>Age: {{ ageWithYear }}</p>
    <p v-if="item.party">Party: {{ item.party }}</p>
    <div v-if="item.opinionPool">
      Opinion pool:
      <progress max="100" :value="item.opinionPool"></progress>
      {{ item.opinionPool }}%
    </div>
  </div>
</template>

<script>

import { computed } from 'vue';

export default {
  name: 'SingleElement',
  props: {
    item: {
      type: Object,
      default: () => {},
    },
    index: {
      type: Number,
      default: 0,
    },
  },
  setup(props) {
    const ageWithYear = computed(() => `${props.item.age} years`);

    return ({ ageWithYear });
  },
};

</script>

<style lang="scss">
  .single-item {
    border: 1px solid black;
    padding: 10px;
  }
</style>
