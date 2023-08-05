<script setup>
const props = defineProps(['operador','somar','subtrair','dividir','multiplicar']);
</script>
<template>
  <div class="alert alert-light mt-3" role="alert">
    Resultado:
    <span v-if="props.operador==='somar'">{{ props.somar }}</span>
    <span v-else-if="props.operador==='subtrair'">{{ props.subtrair }}</span>
    <span
      v-else-if="props.operador==='multiplicar'"
      >{{ props.multiplicar }}</span
    >
    <span v-else>{{ props.dividir }}</span>
  </div>
</template>

<style scoped>
span {
  font-weight: bold;
  font-size: 24px;
}
</style>
