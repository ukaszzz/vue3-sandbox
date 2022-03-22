<template>
<button>{{text}}
  <slot>
    <slot name="text">{{text}}</slot>
    <slot name="image"></slot>
  </slot>
</button>
</template>

<script>

export default {
  name: 'ButtonComponent',
  props: {
    text: {
      type: String,
      default: 'text',
    },
  },
  setup() {
    return { };
  },
};
</script>

<style lang="scss">
button{ height: 50px;
width:250px;
background: cadetblue}
</style>
