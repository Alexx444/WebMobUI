<script setup>
import { computed, ref } from 'vue';

const baseKelvin = ref(0);
const celsiusValue = computed(() => baseKelvin.value - 273.15);
const fahrenheitValue = computed(() => (baseKelvin.value * 9) / 5 - 459.67);


function updateBaseKelvin(event) {
  baseKelvin.value = event.target.value;
}
</script>

<template>
  <label>Kelvin</label>
  <input type="number" :value="baseKelvin" @input="updateBaseKelvin($event)"/>
  <label>Celsius</label>
  <input type="number" :value="celsiusValue"/>
  <label>Fahrenheit</label>
  <input type="number" :value="fahrenheitValue"/>
</template>

<style scoped>
  * {
    display: block;
  }
  label {
    margin-top: 1rem;
  }
</style>
