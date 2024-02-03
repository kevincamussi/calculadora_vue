<script setup>
    const props = defineProps(['valor1', 'valor2']);
</script>

<template>
    <div class="campos">
        <input @keyup="props.valor1" type="number" class="dados">
        <input @keyup="props.valor2" type="number" class="dados">
    </div>
</template>

<style scoped>
.campos {
    display: flex;
    justify-content: space-around;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
}

.dados {
    -moz-appearance:textfield; 
    margin: 50px 0 20px;
}

@media screen and (max-width:767px) {
    .dados{
        max-width: 40%;
    }
}
</style>