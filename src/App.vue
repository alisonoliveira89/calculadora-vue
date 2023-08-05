<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'
import Resultado from './components/Resultado.vue'

  const estado = reactive({
    primeiroNumero: 0,
    segundoNumero: 0,
    operador: 'somar',
  })

  const somar = () => {
    const result = parseInt(estado.primeiroNumero) + parseInt(estado.segundoNumero);
    const isValid = Number.isInteger(result);//Resolver NaN

    const retSoma = isValid ? result : 0;

    return retSoma
  }

  const subtracao = () => {
    return estado.primeiroNumero - estado.segundoNumero
  }

  const multiplicacao = () => {
    return estado.primeiroNumero * estado.segundoNumero
  }

  const divisao = () => {
    const result = estado.primeiroNumero / estado.segundoNumero
    const isValid = Number.isFinite(result);//Resolver Infinity

    const retDivid = isValid ? result : 0;

    return retDivid
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
    <Cabecalho />
    <Formulario
      :numero1="evento => estado.primeiroNumero = evento.target.value"
      :numero2="evento => estado.segundoNumero = evento.target.value"
      :operador="evento => estado.operador = evento.target.value"
    />
    <Resultado
      :operador="estado.operador"
      :somar="somar()"
      :subtrair="subtracao()"
      :multiplicar="multiplicacao()"
      :dividir="divisao()"
    />
  </div>
</template>
