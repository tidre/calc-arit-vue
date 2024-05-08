<script setup>  
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';
  import Resultado from './components/Resultado.vue';

  const estado = reactive({
    operacao: '',
    valor1Temp: 0,
    valor2Temp: 0,
    resultado: 0,
  })

  const realizaOperacao = () => {
    const { operacao, valor1Temp, valor2Temp } = estado;

    switch (operacao) {
      case 'subtracao':
        return estado.resultado = valor1Temp - valor2Temp;
      case 'multiplicacao':
        return estado.resultado = valor1Temp * valor2Temp;
      case 'divisao':
        return estado.resultado = valor1Temp / valor2Temp;
      default:
        return estado.resultado = valor1Temp + valor2Temp;
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :realiza-operacao="realizaOperacao" :set-valor-1="evento => estado.valor1Temp = parseInt(evento.target.value)" :set-valor-2="evento => estado.valor2Temp = parseInt(evento.target.value)" :trocar-operacao="evento => estado.operacao = evento.target.value" />
    <Resultado :resultado="estado.resultado"/>
  </div>
</template>

<style scoped>
</style>
