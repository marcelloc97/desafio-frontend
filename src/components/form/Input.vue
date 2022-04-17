
<template>
  <input
    class="input-container flex-column"

    :placeholder="label"
    :value="modelValue"
    :type="type"
    :disabled="disabled"

    @input="updateModelValue"
    @click="focus"
    @blur="unfocus"
  />
</template>

<script>
export default {
  name: 'Input',

  props: {
    modelValue: String,

    label: {
      type: String,
      required: true
    },

    type: {
      type: String,
      default: 'text'
    },
    
    disabled: Boolean
  },

  methods: {
    updateModelValue(event) {
      let value = event.target.value;

      if (value === '') {
        value = undefined;
      }

      this.$emit('update:model-value', value);
    },

    focus(e) {
      this.$emit('focus', e);
    },
    unfocus(e) {
      this.$emit('unfocus', e);
    }
  }
}
</script>

<style scoped>
.input-container {
  width: 250px;
  height: 20px;
  padding: 10px;
  position: relative;

  font-size: 0.9em;
  text-align: start;
  color: #3A3A3A;

  border: 1px solid #00000022;
  border-radius: 5px;
  outline: none;

  cursor: text;
  transition: all 0.2s ease-in-out;
}
.input-container:focus {
  border-color: #0C9BF2; 
}
</style>
