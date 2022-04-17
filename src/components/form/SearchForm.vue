
<template>
  <form class="form flex-row justify-between" @submit.prevent="submit">
    <div class="inputs flex-row">
      <Input
        label="Nome"
        :model-value="name"
        @update:model-value="(value) => updateInput('name', value)"
      />

      <Input
        label="Sobrenome"
        :model-value="lastname"
        @update:model-value="(value) => updateInput('lastname', value)"
      />

      <Input
        label="E-mail"
        :model-value="email"
        @update:model-value="(value) => updateInput('email', value)"
      />
    </div>

    <Button outline icon="search" label="Buscar" @click="submit" />
  </form>
</template>

<script>
// import Input from './Input.vue';
import Button from '../button/Button.vue';

export default {
  name: 'SearchForm',
  components: {
    // Input,
    Button
  },

  data() {
    return {
      name: undefined,
      lastname: undefined,
      email: undefined
    };
  },

  methods: {
    submit() {

      console.log('fuck you');

      this.$emit('submit', {
        name: this.name,
        lastname: this.lastname,
        email: this.email
      });

      this.name = undefined;
      this.lastname = undefined;
      this.email = undefined;
    },

    updateInput(name, value) {
      this[name] = value;
    }
  }
}
</script>

<style scoped>
.form {
  min-width: 100%;
}

.inputs > .input-container {
  margin-right: 10px;
}
.inputs > .input-container:last-child {
  margin: 0;
}
</style>
