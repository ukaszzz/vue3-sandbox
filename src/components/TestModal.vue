<template>
  <div class="modal">
    <article class="modal__content">
<section class="modal__text">
  <h1>do you wamt to log in</h1>
</section>
<section class="modal__buttons">
<SimpleButton text="yes"/>
<SimpleButton text="no"/>
</section>
    </article>
  </div>
</template>

<script>
import SimpleButton from '@/components/SimpleButton.vue';

export default {
  name: 'TestModal',
  props: {

  },
  components: {
    SimpleButton,
  },
};
</script>

<style lang="scss">
.modal{
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #ddd;

&__content{
  width: 500px;
  height: 500px;
  background: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
}}
</style>
