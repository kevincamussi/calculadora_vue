<script setup>
    const props = defineProps(['operacao']);
</script>

<template>
    <select  @change="props.operacao "  class="seletor" >
        <option value="seletor">Selecione a operação</option>
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="divisao">Divisão</option>
        <option value="multiplicacao">Multiplicação</option>
    </select>
</template>
<style scoped>
.seletor{
    width: 90%;
    text-align: center;
    padding: 4px;
}

</style>