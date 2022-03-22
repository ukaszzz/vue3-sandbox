<template>
  <div class="search">
    <label :for="name">
      <input
        :id="name"
        :name="name"
        :placeholder="placeholder"
        :type="type"
        class="input"
        @input="(e)=> $emit('update:firstName', e.target.value)"
        :value="firstName"
      />
    </label>
    <label :for="name">
      <input
        :id="name"
        :name="name"
        :placeholder="placeholder"
        :type="type"
        class="input"
        @input="(e)=> $emit('update:lastName', e.target.value)"
        :value="lastName"
      />
    </label>
  </div>
</template>

<script>

export default {
  name: 'BaseInput',
  props: {
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      default: 'text',
    },
    placeholder: {
      type: String,
      default: 'Type something...',
    },
    firstName: {
      type: String,
    },
    lastName: {
      type: String,
    },
    modelValue: {
      type: String,
    },
  },

};
</script>
