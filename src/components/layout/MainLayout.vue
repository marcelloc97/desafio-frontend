
<template>
  <div id="layout">
    <Header username="Marcello Carvalhal" />

    <section class="content">
      <header class="flex-row justify-between align-center">
        <h2>Carteiras BTC</h2>
        <Button label="Adicionar Carteira" />
      </header>

      <main>
        <Container row justify-between align-center>
          <div class="inputs flex-row align-center">
            <Input label="Nome" />
            <Input label="Sobrenome" />
            <Input label="E-mail" />
          </div>

          <Button outline icon="search" label="Buscar" />
        </Container>

        <Container class="table-container">
          <table>
            <thead>
              <th>a</th>
            </thead>
            <tbody>
              <td>b</td>
            </tbody>
          </table>
        </Container>
      </main>

      <footer>
        Powered by:
        <a
          href="https://github.com/marcelloc97"
          target="_blank"
        >
          Marcello Carvalhal
        </a>
      </footer>
    </section>
  </div>
</template>

<script>
import Header from '../misc/Header.vue';
import Button from '../button/Button.vue';
import Container from '../misc/Container.vue';
import Input from '../form/Input.vue';

export default {
  name: 'MainLayout',

  components: {
    Header,
    Button,
    Container,
    Input
  },

  props: {},

  computed: {},

  data() {
    return {};
  },

  methods: {}
}
</script>

<style scoped>
#layout {
  width: 100%;
  height: 100vh;

  background: #F5F6F8;
  color: #3A3A3A;
}

.content {
  margin-top: 35px;
  padding: 0 100px;
}
.content > main {
  margin-top: 10px;
}

.inputs > .input-container {
  margin-right: 10px;
}
.inputs > .input-container:last-child {
  margin: 0;
}

.table-container {
  margin-top: 20px;
}
</style>