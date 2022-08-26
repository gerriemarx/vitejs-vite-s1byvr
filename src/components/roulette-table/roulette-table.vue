<script>
import RouletteTableColumn from './roulette-table-column.vue';
import {
  VALUES,
  COLOR,
  PARITY,
  COLUMN,
  ROW,
  LEVEL,
} from './models/table-constants.js';

export default {
  components: {
    RouletteTableColumn,
  },
  computed: {
    zero() {
      return VALUES[0];
    },
    firstColumn() {
      return VALUES.filter((x) => x.column == '1st');
    },
    secondColumn() {
      return VALUES.filter((x) => x.column == '2nd');
    },
    thirdColumn() {
      return VALUES.filter((x) => x.column == '3rd');
    },
  },
};
</script>

<template>
  <div class="table">
    <div class="zero">
      {{ zero.number }}
    </div>
    <RouletteTableColumn :values="firstColumn" />
    <RouletteTableColumn :values="secondColumn" />
    <RouletteTableColumn :values="thirdColumn" />
  </div>
</template>

<style scoped>
.table {
  display: flex;
  flex-direction: row;
}

.table > .zero {
  border: 2px solid black;
  padding: 10px;
  padding-top: 55px;
  width: 25px;
  text-align: center;
  border-radius: 30px 0 0 30px;
  margin-right: 1px;
}
</style>
