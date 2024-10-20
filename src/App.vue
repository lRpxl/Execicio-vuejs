
<script>
import EntradaNum from './components/entradaNum.vue';
import Selecao from './components/selecao.vue';

export default {
  components: {
    EntradaNum,
    Selecao
  },
  data() {
    return {
      num1: '',    // Inicializar como string vazia para permitir entrada de dados
      num2: '',    // Inicializar como string vazia
      operation: '+'
    };
  },
  computed: {
    result() {
      const n1 = parseFloat(this.num1) || 0;
      const n2 = parseFloat(this.num2) || 0;

      switch (this.operation) {
        case '+':
          return n1 + n2;
        case '-':
          return n1 - n2;
        case '*':
          return n1 * n2;
        case '/':
          return n2 !== 0 ? n1 / n2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  },
  methods: {
    setOperation(op) {
      this.operation = op;
    }
  }
};
</script>

<template>
  <div class="calculator">
    <h2>Calculadora Aritmetica</h2>
    <!-- Primeiro campo de número -->
    <EntradaNum v-model="num1" />

    <!-- Campo de seleção de operação -->
    <Selecao @select-operation="setOperation" />

    <!-- Segundo campo de número -->
    <EntradaNum v-model="num2" />

    <!-- Exibição do resultado -->
    <p class="result">Resultado: {{ result }}</p>
  </div>
</template>

<style scoped>
.calculator {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  width: 300px;
  margin: 0 auto;
}
.result {
  text-align: center;
  font-size: 1.5rem;
  color: #4caf50;
}
</style>