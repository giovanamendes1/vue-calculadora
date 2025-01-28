<script>
import NumberInput from './components/NumberInput.vue';
import OperationSelect from './components/OperationSelect.vue';
import ResultDisplay from './components/ResultDisplay.vue';

export default {
  components: {
    NumberInput,
    OperationSelect,
    ResultDisplay,
  },
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      const { number1, number2, operation } = this;
      switch (operation) {
        case "add":
          return number1 + number2;
        case "subtract":
          return number1 - number2;
        case "multiply":
          return number1 * number2;
        case "divide":
          return number2 !== 0 ? number1 / number2 : "Erro (divisão por 0)";
        default:
          return 0;
      }
    },
  },
};
</script>
<template>
  <div class="container mt-5">
    <h1 class="text-center">Calculadora Aritmética</h1>
    <div class="row justify-content-center">
      <div class="col-md-6">
        <NumberInput
          v-model="number1"
          placeholder="Número 1"
        />
        <OperationSelect v-model="operation" />
        <NumberInput
          v-model="number2"
          placeholder="Número 2"
        />
        <ResultDisplay :result="result" />
      </div>
    </div>
  </div>
</template>


<style>
h1 {
  font-family: Arial, sans-serif;
}
</style>