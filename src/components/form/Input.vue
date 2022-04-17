
<template>
  <div :class="containerClasses" @click="focus">
    <span v-if="showingLabel" v-text="label" />
    <input
      v-if="!showingLabel"
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

  computed: {
    containerClasses() {
      const classes = [
        'input-container',
        'flex-column'
      ];

      if (this.isFocused) {
        classes.push('focus');
      }

      return classes;
    },

    showingLabel() {
      return Boolean(!this.modelValue) && !this.isFocused;
    }
  },

  data() {
    return {
      isFocused: false,
    };
  },

  methods: {
    updateModelValue(event) {
      let value = event.target.value.replace(/[\n\r\s\t]+/gi, '');

      if (value === '') {
        value = undefined;
      }

      this.$emit('update:model-value', value);
    },

    focus() {
      if (!this.isFocused) {
        this.isFocused = true;

        this.$nextTick(() => {
          this.$refs.input.focus();
        });
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

  font-size: 0.9em;
  text-align: start;
  color: #3A3A3Aaa;

  border: 1px solid #00000022;
  border-radius: 5px;

  cursor: text;
  transition: all 0.2s ease-in-out;
}
.input-container > span {
  user-select: none;
}

.input-container > input {
  color: #3A3A3A;

  background: none;
  border: none;
  outline: none;
}

.focus {
  border-color: #0C9BF2; 
}
</style>
