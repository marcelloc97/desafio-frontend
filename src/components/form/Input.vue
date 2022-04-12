
<template>
  <div class="input-container flex-column" @click="focus">
    <span :class="spanClasses" v-text="label" />
    <input
      ref="input"

      :value="modelValue"
      :type="type"
      :disabled="disabled"

      @change="updateModelValue"
      @blur="unfocus"
    />
  </div>
</template>

<script>
export default {
  name: 'Input',

  props: {
    modelValue: [String, Number],

    label: {
      type: String,
      required: true
    },

    type: String,
    disabled: Boolean,

    filled: Boolean,
    outline: Boolean
  },

  computed: {
    spanClasses() {
      return this.isFocused ? 'focused' : '';
    }
  },

  data() {
    return {
      isFocused: Boolean(this.modelValue),
    };
  },

  methods: {
    updateModelValue(newVal) {
      this.$emit('update:model-value', newVal);
    },

    focus() {
      if (!this.isFocused) {
        this.isFocused = true;

        this.$nextTick(() => {
          this.$refs.input.focus();
        })
      }
    },

    unfocus() {
      if (this.isFocused) {
        this.isFocused = false;
      }
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

  font-size: 0.8em;
  text-align: start;
  color: #3A3A3Aaa;

  border: 1px solid #00000022;

  cursor: text;
  transition: all 0.2s ease-in-out;
}
.input-container:focus {
  border-color: #09f;
}
.input-container > span {
  user-select: none;
}
.input-container > input {
  margin-top: 5px;

  background: none;
  border: none;
  outline: none;
}

.focused {
  margin: 5px 11px;
  position: absolute;
  top: 0;
  left: 0;

  font-size: 0.75em;
}
</style>
