<template>
  <div class="calculator">
    <input type="number" v-model="numero1" @input="calcular">
    <select v-model="operacao" @change="calcular">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input type="number" v-model="numero2" @input="calcular">
    <div>Resultado: {{ resultado }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0
    };
  },
  methods: {
    calcular() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = Number(this.numero1) + Number(this.numero2);
          break;
        case 'subtracao':
          this.resultado = Number(this.numero1) - Number(this.numero2);
          break;
        case 'multiplicacao':
          this.resultado = Number(this.numero1) * Number(this.numero2);
          break;
        case 'divisao':
          this.resultado = Number(this.numero1) / Number(this.numero2);
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>

<style>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>

  