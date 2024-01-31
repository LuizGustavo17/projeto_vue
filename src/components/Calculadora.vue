<template>
  <div class="calculadora">
    <input type="number" v-model.number="numero1" @input="calcular">
    <select v-model="operacao" @change="calcular">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input type="number" v-model.number="numero2" @input="calcular">
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
          this.resultado = this.numero1 + this.numero2;
          break;
        case 'subtracao':
          this.resultado = this.numero1 - this.numero2;
          break;
        case 'multiplicacao':
          this.resultado = this.numero1 * this.numero2;
          break;
        case 'divisao':
          this.resultado = this.numero1 / this.numero2;
          break;
      }
    }
  }
};
</script>

<style scoped>
.calculadora {
  margin: 20px auto;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 300px;
}

input[type="number"], select {
  margin: 5px;
  padding: 5px;
  width: 100px;
}
</style>
