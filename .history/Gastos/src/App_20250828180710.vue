<template>
  <div id="app">
    <h1>Painel de Gastos Mensais</h1>
    <Login v-if="!autenticado" @autenticado="autenticado = true" />
    <GastosDashboard v-else />
  </div>
</template>

<script>
import GastosDashboard from './components/GastosDashboard.vue';
import Login from './components/Login.vue';

export default {
  name: 'App',
  components: {
    GastosDashboard,
    Login
  },
  data() {
    return {
      autenticado: false
    };
  }
};
</script>

<style>
#app {
  font-family: 'Segoe UI', Arial, sans-serif;
  background: #f7f7f7;
  min-height: 100vh;
  padding: 2rem;
}
h1 {
  color: #2c3e50;
  margin-bottom: 2rem;
}
</style>
