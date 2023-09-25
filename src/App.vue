<script setup>
import { reactive} from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'

const estado = reactive({
  primeiroNumero: '',
  segundoNumero: '',
  operacao: 'soma',
  resultado: ''
})

const calculaResultado = () => {
  const { operacao, primeiroNumero, segundoNumero } = estado;

  switch (operacao) {
    case 'soma':
      return primeiroNumero + segundoNumero;
    case 'subtracao':
      return primeiroNumero - segundoNumero;
    case 'multiplicacao':
      return primeiroNumero * segundoNumero;
    case 'divisao':
      return primeiroNumero / segundoNumero;
    default:
      return null;
  }
}
</script>

<template>
  <div class="container mx-auto my-6">
    <Cabecalho/>
    <Formulario :operacao="evento => estado.operacao = evento.target.value" :primeiro-numero="evento => estado.primeiroNumero = Number(evento.target.value)" :segundo-numero="evento => estado.segundoNumero = Number(evento.target.value)" :resultado="calculaResultado()"/>
  </div>
</template>

<style scoped>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>
