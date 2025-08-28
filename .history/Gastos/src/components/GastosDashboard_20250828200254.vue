<template>
  <div class="dashboard">

<script>

import GraficoGastos from './GraficoGastos.vue';
import ExportarRelatorio from './ExportarRelatorio.vue';
import GoogleCalendarPanel from './GoogleCalendarPanel.vue';
import { criarLembreteGasto } from '../services/googleCalendar';

export default {
  name: 'GastosDashboard',
  components: { GraficoGastos, ExportarRelatorio, GoogleCalendarPanel },
  data() {
    return {
      gastos: [],
      novoGasto: {
        descricao: '',
        valor: 0,
        categoria: ''
      }
    };
  },

      this.gastos.push({ ...this.novoGasto });
      this.novoGasto = { descricao: '', valor: 0, categoria: '' };
    },
    removerGasto(index) {
      this.gastos.splice(index, 1);
    },
    async criarLembrete(gasto) {
      await criarLembreteGasto(gasto);
      alert('Lembrete criado no Google Calendar!');
    }
  }
};
</script>

<style scoped>
.dashboard {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  padding: 2rem;
  max-width: 600px;
  margin: auto;
}
form {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
}
input, button {
  padding: 0.5rem;
  border-radius: 4px;
  border: 1px solid #ccc;
}
button {
  background: #2c3e50;
  color: #fff;
  border: none;
  cursor: pointer;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin-bottom: 0.5rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.grafico {
  margin-top: 2rem;
  min-height: 200px;
  background: #f0f0f0;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #888;
}
</style>
