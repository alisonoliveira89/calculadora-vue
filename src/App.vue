<script setup>
import { reactive } from 'vue';


  const estado = reactive({
    primeiroNumero: 1,
    segundoNumero: 3,
    operacao: 'somar'
  })

  const somar = () => {
    return estado.primeiroNumero + estado.segundoNumero
  }

  const subtracao = () => {
    return estado.primeiroNumero - estado.segundoNumero
  }

  const multiplicacao = () => {
    return estado.primeiroNumero * estado.segundoNumero
  }

  const divisao = () => {
    return estado.primeiroNumero / estado.segundoNumero
  }

  const operacao = () => {
    const {somar} = estado;

    switch (somar) {
      case 'subtrair':
        return subtracao();
      case 'multiplicar':
        return multiplicacao();
      case 'dividir':
        return divisao();
    }
  }
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora Aritmética - VueJS</h1>
    </header>

    <form @submit.prevent="">
      <div class="row">
        <div class="col">
          <input
            :value="estado.primeiroNumero"
            type="number"
            placeholder="digite o numero"
            class="form-control"
          />
        </div>
        <div class="col">
          <input
            :value="estado.segundoNumero"
            type="number"
            placeholder="digite o numero"
            class="form-control"
          />
        </div>
        <div class="col">
          <select class="form-select">
            <option value="somar">+ Adição</option>
            <option value="subtrair">- Subtração</option>
            <option value="multiplicar">x Multiplicação</option>
            <option value="dividir">% Divisão</option>
          </select>
        </div>
      </div>
    </form>
    <div class="alert alert-light mt-3" role="alert">
      Resultado: {{ somar() }}
    </div>
    {{ operacao() }}
  </div>
</template>

<style scoped></style>
