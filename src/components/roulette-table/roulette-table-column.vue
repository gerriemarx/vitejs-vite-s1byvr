<script>
export default {
  props: ['values'],
  computed: {
    firstRow() {
      return this.values.filter((x) => x.row == '1st');
    },
    secondRow() {
      return this.values.filter((x) => x.row == '2nd');
    },
    thirdRow() {
      return this.values.filter((x) => x.row == '3rd');
    },
  },
};
</script>

<template>
  <div class="column">
    <div class="row">
      <div class="item" v-for="t of thirdRow">
        {{ t.number }}
      </div>
    </div>
    <div class="row">
      <div class="item" v-for="s of secondRow">
        {{ s.number }}
      </div>
    </div>
    <div class="row">
      <div class="item" v-for="f of firstRow">
        {{ f.number }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.column {
  display: flex;
  flex-direction: column;
  margin: 1px;
  border: 1px solid black;
}
.row {
  display: flex;
  flex-direction: row;
  border: 1px solid black;
  width: 180px;
}
.item {
  border: 1px black solid;
  width: 25px;
  padding: 10px;
  text-align: center;
}
</style>
