<script setup>
  const props = defineProps(['primeiroNumero', 'segundoNumero', 'operacao', 'resultado']);
</script>

<template>
  <form class="my-2">
    <div class="flex">
      <input type="number" @keyup="props.primeiroNumero" required placeholder="Digite o primeiro número" class="border rounded-lg p-2 bg-sky-50 text-gray-600 placeholder:text-neutral-400">
      <input type="number" @keyup="props.segundoNumero" required placeholder="Digite o primeiro número" class="border rounded-lg p-2 bg-sky-50 text-gray-600 mx-3 placeholder:text-neutral-400">
      <select class="block p-2 border rounded-lg focus:ring focus:ring-blue-200" @change="props.operacao">
        <option value="soma">Somar</option>
        <option value="subtracao">Subtrair</option>
        <option value="multiplicacao">Multiplicar</option>
        <option value="divisao">Dividir</option>
      </select>
    </div>
    <div>
      <p class="text-2xl mt-4" v-if="props.resultado !== null ">Resultado: {{ props.resultado}}</p>
    </div>
  </form>
</template>

<style scoped>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>