<template>
  <div>
    <MultiSelect
      v-model="selectedValues"
      :options="options"
      optionLabel="name"
      placeholder="Выберите значения"
      @change="onSelectionChange"
      aria-label="Options"
    />
    <Button v-if="selectedValues.length" @click="clearSelection">✖</Button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import MultiSelect from 'primevue/multiselect';
import Button from 'primevue/button';
const options = ref([
  { name: 'Значение 1', code: 'VAL1' },
  { name: 'Значение 2', code: 'VAL2' },
  { name: 'Значение 3', code: 'VAL3' },
  { name: 'Значение 4', code: 'VAL4' },
]);

const selectedValues = ref([]);

function clearSelection() {
  selectedValues.value = [];
}

function onSelectionChange() {
  console.log('Выбранные значения:', selectedValues.value);
}
</script>

<style>
</style>
