<script setup>
const props = defineProps(['numero1','numero2','operador']);
</script>
<template>
  <form>
    <div class="row">
      <div class="col">
        <input
          @keyup="props.numero1"
          @change="props.numero1"
          type="number"
          placeholder="digite o numero"
          class="form-control"
        />
      </div>
      <div class="col">
        <input
          @keyup="props.numero2"
          @change="props.numero2"
          type="number"
          placeholder="digite o numero"
          class="form-control"
        />
      </div>
      <div class="col">
        <select @change="props.operador" class="form-select">
          <option value="somar">+ Adição</option>
          <option value="subtrair">- Subtração</option>
          <option value="multiplicar">x Multiplicação</option>
          <option value="dividir">% Divisão</option>
        </select>
      </div>
    </div>
  </form>
</template>
