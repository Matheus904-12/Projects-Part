<template>
  <div id="app">
    <h1>Painel de Gastos Mensais</h1>
    <GastosDashboard />
  </div>
</template>

<script>
import GastosDashboard from './components/GastosDashboard.vue';

export default {
  name: 'App',
  components: {
    GastosDashboard
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
