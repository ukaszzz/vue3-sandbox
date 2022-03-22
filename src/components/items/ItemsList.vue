<template>
  <div class="items">
    <SingelElement
      v-for="(item, index) in items"
      :key="item.id"
      :index="index"
      :item="item"
    />
  </div>
</template>

<script>
import SingelElement from '@/components/items/item/SingelElement.vue';

export default {
  name: 'ItemsList',
  components: {
    SingelElement,
  },
  props: {
    items: {
      type: Array,
      default: () => [{
        id: 1,
        firstName: 'test',
        lastName: 'test',
        age: 44,
        party: 'test',
        opinionPool: 4,
      }],
    },
  },
};

</script>

<style lang="scss" scoped>
.items {
  font-family: arial,serif;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 25px;
  max-width: 1200px;
  margin: 0 auto;
&__card {
   border: 1px solid black;
   padding: 10px;
 }
}
</style>
