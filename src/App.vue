<!--
@file App.vue
@author Samuel Tonon
@date 2026-03-17

@description
Componente principal da calculadora aritmética.
Gerencia o estado global e o cálculo automático.

@tech
Vue.js, Bootstrap
-->

<script setup>
import { reactive, computed } from 'vue'

import Cabecalho from './components/Cabecalho.vue'
import Calculadora from './components/Calculadora.vue'
import Resultado from './components/Resultado.vue'

// ESTADO
const estado = reactive({
  numero1: null,
  numero2: null,
  operacao: '+'
})

// LIMPAR
function limparCalculadora() {
  estado.numero1 = null
  estado.numero2 = null
  estado.operacao = '+'
}

// RESULTADO AUTOMÁTICO
const resultado = computed(() => {
  const { numero1, numero2, operacao } = estado

  if (numero1 === null || numero2 === null) {
    return 'Digite os números'
  }

  switch (operacao) {
    case '+': return numero1 + numero2
    case '-': return numero1 - numero2
    case '*': return numero1 * numero2
    case '/':
      return numero2 === 0
        ? 'Divisão por zero não permitida'
        : numero1 / numero2
    default:
      return 0
  }
})
</script>

<template>
  <div class="container mt-5 d-flex justify-content-center">

    <div class="win-box p-3 col-md-6">

      <div class="win-header mb-3 text-center">
        calculadora.exe
      </div>

      <Cabecalho />

      <Calculadora :estado="estado" :limpar-calculadora="limparCalculadora" />

      <Resultado :resultado="resultado" />

    </div>

  </div>
</template>
