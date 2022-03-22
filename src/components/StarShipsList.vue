<template>
  <section>
    <h1>ships list:</h1>
    <SingleShip :ship="ships"/>
  </section>
</template>

<script>
import SingleShip from '@/components/SingleShip.vue';
import { ref } from 'vue';

export default {
  name: 'StarShipsList',
  components: {
    SingleShip,
  },
  props: {

  },
  async setup() {
    const ships = ref(null);

    const response = await fetch('http://swapi.dev/api/starships/9');
    console.log(response);
    const pasedResponse = await response.json();

    ships.value = [...pasedResponse.results];
    return { ships };
  },
};
</script>

<style lang="scss">

</style>
