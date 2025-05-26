<template>
  <div>
    <form @submit.prevent>
      <input type="text" id="inputText" v-model="inputText" placeholder="Escribe algo...">
    </form>

    <p>Cantidad caracteres = {{ charCount }}</p>
    <br>
    <div v-if="inputText.length > 0">
      <p>1 - {{ textoCodificado }} (codificado)</p>
      <p>2 - {{ textoMayuscula }} (mayuscula)</p>
      <p>3 - {{ textoMinuscula }} (minuscula)</p>
      <p>4 - {{ textoMayusculaIntercalada }} (mayuscula / minuscula)</p>
      <p>5 - {{ textoMinusculaIntercalada }} (minuscula / mayuscula)</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModificadorDeTexto',
  data() {
    return {
      inputText: ''
    };
  },
  computed: {
    charCount() {
      return this.inputText.length;
    },
    textoCodificado() {
      const lowerText = this.inputText.toLowerCase();
      let resultado = '';
      for (let i = 0; i < lowerText.length; i++) {
        let char = lowerText[i];
        switch (char) {
          case 'a':
            resultado += 'u';
            break;
          case 'e':
            resultado += 'o';
            break;
          case 'i':
            resultado += 'i';
            break;
          case 'o':
            resultado += 'e';
            break;
          case 'u':
            resultado += 'a';
            break;
          default:
            resultado += char;
        }
      }
      return resultado;
    },
    textoMayuscula() {
      return this.inputText.toUpperCase();
    },
    textoMinuscula() {
      return this.inputText.toLowerCase();
    },
    textoMayusculaIntercalada() {
      let result = '';
      for (let i = 0; i < this.inputText.length; i++) {
        if (i % 2 === 0) {
          result += this.inputText[i].toUpperCase();
        } else {
          result += this.inputText[i].toLowerCase();
        }
      }
      return result;
    },
    textoMinusculaIntercalada() {
      let result = '';
      for (let i = 0; i < this.inputText.length; i++) {
        if (i % 2 === 0) {
          result += this.inputText[i].toLowerCase();
        } else {
          result += this.inputText[i].toUpperCase();
        }
      }
      return result;
    }
  }
};
</script>

<style >

</style>