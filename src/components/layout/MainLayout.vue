
<template>
  <div id="layout">
    <Header />

    <section class="content">
      <header>
        <h2>Carteiras BTC</h2>
        <Button label="Adicionar Carteira" />
      </header>

      <main>
        <Container>

        </Container>
      </main>

    </section>
  </div>
</template>

<script>
import Header from '../misc/Header.vue';
import Button from '../button/Button.vue';
import Container from '../misc/Container.vue';

export default {
  name: 'MainLayout',

  components: {
    Header,
    Button,
    Container
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

#layout > .content {
  margin-top: 45px;
  padding: 0 100px;
}

.content > header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.content > main {
  margin-top: 10px;
}
</style>