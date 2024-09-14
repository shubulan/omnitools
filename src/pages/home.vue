<script setup>
import _ from "loadsh";
import { ref } from "vue";
const n = 5 * 5;
let points = Array.from({ length: n }, (_, i) => ({
  value: i + 1,
  color: false,
}));
points = _.shuffle(points);

const boxs = ref(points);
let click_num = 1;

function handleClick(item) {
  console.log(item);
  if (item.value === click_num) {
    click_num++;
    item.color = true;
  }
}
</script>

<template>
  <div class="container">
    <div
      :class="['boxs', item.color ? 'active' : '']"
      v-for="(item, idx) in boxs"
      :key="idx"
      @click="handleClick(item)"
    >
      {{ item.value }}
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  width: 520px;
  flex-wrap: wrap;
}
.boxs {
  height: 100px;
  width: 100px;
  border: 2px black solid;
  box-sizing: border-box;
  align-content: center;
  font-size: 225%;
}

.active {
  background-color: red;
}
</style>
