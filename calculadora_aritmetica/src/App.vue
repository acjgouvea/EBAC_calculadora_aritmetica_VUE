<script setup>
import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operator = ref('addition');

const result = computed(() => {
  switch (operator.value) {
    case 'addition':
      return num1.value + num2.value;
    case 'subtraction':
      return num1.value - num2.value;
    case 'multiplication':
      return num1.value * num2.value;
    case 'division':
      return num1.value / num2.value;
    default:
      return 0;
  }
});
</script>

<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-4 offset-md-4">
        <div class="form-group">
          <input type="number" class="form-control" v-model.number="num1" placeholder="Número 1">
        </div>
        <div class="form-group">
          <select class="form-control" v-model="operator">
            <option value="addition">+</option>
            <option value="subtraction">-</option>
            <option value="multiplication">*</option>
            <option value="division">/</option>
          </select>
        </div>
        <div class="form-group">
          <input type="number" class="form-control" v-model.number="num2" placeholder="Número 2">
        </div>
        <div class="form-group">
          <label>Resultado:</label>
          <input type="text" class="form-control" :value="result" disabled>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
