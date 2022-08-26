<script>
import SpinResultTable from '../components/SpinResultTable.vue';
import RouletteTable from '../components/roulette-table/roulette-table.vue';

export default {
  components: {
    SpinResultTable,
    RouletteTable,
  },
  data() {
    return {
      spinResult: null,
      spinResultHistory: [],
    };
  },
  methods: {
    captureSpinResult(event) {
      if (this.spinResult == null || this.spinResult == undefined) return;

      if (this.spinResult <= 36 && this.spinResult >= 0) {
        this.spinResultHistory.push(this.spinResult);
      }

      this.spinResult = null;
    },
  },
};
</script>

<template>
  <label for="spinResultInput">Spin result: </label>
  <input
    id="spinResultInput"
    type="number"
    v-model="spinResult"
    min="0"
    max="36"
    @keydown.enter="captureSpinResult"
  />

  <RouletteTable />
  <SpinResultTable :spin-result-history="spinResultHistory" />
</template>
