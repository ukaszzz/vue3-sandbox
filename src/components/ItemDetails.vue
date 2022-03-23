<template>
  <section v-if="item">
    <p>{{item.name}}</p>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'ItemDetails',
  props: {
    id: {
      typ: String,
    },
  },
  async setup(props) {
    const item = ref(null);
    const respone = await fetch(`https://swapi.dev/api/people/${props.id}`);
    const parsedResponse = await respone.json();

    item.value = parsedResponse;

    return {
      item,
    };
  },
};
</script>
