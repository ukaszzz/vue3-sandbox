<template>
<div>test</div>
  <button @click="sayHello">hello</button>
  <button @click="addMark('text')">hello</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  setup() {
    function sayHello() {
      console.log('hello');
    }

    function addMark(text) {
      console.log(`function with argument ${text}`);
    }
    return {
      sayHello,
      addMark,
    };
  },

};
</script>
