<template>
  <section v-if="item">
    <p>{{item.name}}</p>
  </section>
  <section v-else>
    <p>ops!!</p>
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
    try {
      const respone = await fetch(`https://swapi.dev/api/people/${props.id}`);
      if (respone.status !== 200) {
        throw new Error('response is different than 200');
      }
      const parsedResponse = await respone.json();
      item.value = parsedResponse;
    } catch (e) {
      console.log(e);
    }

    return {
      item,
    };
  },
};
</script>
