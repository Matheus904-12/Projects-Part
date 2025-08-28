<template>
  <div class="dashboard">

  </div>
</template>

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
