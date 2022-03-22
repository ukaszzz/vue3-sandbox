<template>
  <ItemsList :items="candidates"/>
</template>

<script>
import { ref, computed } from 'vue';
import ItemsList from './items/ItemsList.vue';

export default {
  name: 'CustomComponent',
  components: {
    ItemsList,
  },
  setup() {
    const candidates = ref([
      {
        id: 1,
        firstName: 'test',
        lastName: 'test',
        age: 44,
        party: 'test',
        opinionPool: 4,
      },
      {
        id: 2,
        firstName: 'test',
        lastName: 'test',
        age: 37,
        party: 'test',
        opinionPool: 7,
      },
      {
        id: 3,
        firstName: 'test',
        lastName: 'test',
        age: 47,
        party: null,
        opinionPool: 49,
      },
      {
        id: 4,
        firstName: 'test',
        lastName: 'test',
        age: 43,
        party: null,
        opinionPool: 22,
      },
      {
        id: 5,
        firstName: 'test',
        lastName: 'test',
        age: 61,
        party: 'test',
        opinionPool: null,
      },
      {
        id: 6,
        firstName: 'test',
        lastName: 'test',
        age: 63,
        party: 'test',
        opinionPool: 5,
      },
      {
        id: 7,
        firstName: 'test',
        lastName: 'test',
        age: 38,
        party: 'test',
        opinionPool: 12,
      },
      {
        id: 8,
        firstName: 'test',
        lastName: 'test',
        age: 64,
        party: 'test',
        opinionPool: null,
      },
      {
        id: 9,
        firstName: 'test',
        lastName: 'test',
        age: 44,
        party: null,
        opinionPool: 1,
      },
      {
        id: 10,
        firstName: 'test',
        lastName: 'test',
        age: 64,
        party: 'test',
        opinionPool: null,
      },
    ]);
    const candidatesWithParty = computed(() => candidates.value.filter(({ party }) => party));
    return { candidates, candidatesWithParty };
  },
};
</script>

<style lang="scss">

</style>
