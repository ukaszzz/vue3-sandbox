<template>
<div class="notification">
{{notification}}
  <button @click="$emit('hide-notification')">hide</button>
</div>
</template>

<script>

export default {
  name: 'BaseNotification',
  props: {
    notification: {
      type: String,
    },
  },
};
</script>

<style lang="scss">
.notification{
  position: fixed;
  bottom: 0;
}
</style>
