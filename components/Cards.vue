<script setup>
import { ref, computed, watch } from 'vue'

  const toggleSubgrid = ref(true)
</script>

<template>

  <label>Toggle subgrid
    <input type="checkbox" v-model="toggleSubgrid" class="m-2" />
  </label>


  <div class="wrapper mt-4">
  <div class="box a">A</div>
  <div class="box b">B</div>
  <div class="box c">C</div>
  <div class="box d" :class="toggleSubgrid && 'grid-rows-subgrid grid-cols-subgrid'">
    <div class="box e">E</div>
    <div class="box f">F</div>
    <div class="box g">G</div>
  </div>
</div>
</template>

<style scoped>
 .wrapper {
    display: grid;
    gap: 10px;
    grid-template-columns: 2fr 1fr 2fr 1fr ;
    grid-template-rows: repeat(3,minmax(100px,auto));
  }

  .box {
    background-color: #444;
    color: #fff;
    border-radius: 5px;
    padding: 20px;
    font-size: 150%;

  }

  .box .box {
    background-color: #ccc;
    color: #444;
  }

  .a {
    grid-column: 1 / 3;
  }

  .b {
    border: 0;
    grid-column: 4 ;
  }

  .c {
    grid-column: 1;
    grid-row: 2 / 4;
  }

  .d{
    grid-column: 2 / 5;
    grid-row: 2 / 4;
    display: grid;
  }

  .e {
    grid-row: 1 / 3;
    grid-column: 1 ;
  }

  .f {
    grid-row: 1;
    grid-column: 2 / 4;
  }

  .g {
    grid-row: 2;
    grid-column: 3;
  }
</style>
