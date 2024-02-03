<script setup>
import { reactive } from 'vue';
import Campos from './components/Campos.vue';
import Seletor from './components/Seletor.vue';
import CampoResultado from './components/CampoResultado.vue';

const estado = reactive({
  valor1:'',
  valor2:'',
  operacao:'',
})

const calcular = () => {
  const { operacao } = estado;
  switch (operacao) {
    case 'adicao':
      return somar();
    case 'subtracao':
      return subtrair();
    case 'divisao':
      return dividir()
    case 'multiplicacao':
      return multiplicar();
  }  
}

const somar = () => {
  const { valor1, valor2 } = estado;
  return valor1 + valor2;
}

const subtrair = () => {
  const { valor1, valor2 } = estado;
  return valor1 - valor2;
}

const dividir = () => {
  const { valor1, valor2 } = estado;
  return valor1 / valor2;
}

const multiplicar = () => {
  const { valor1, valor2 } = estado;
  return valor1 * valor2;
}

</script>

<template>
  <div class="container">
    <Campos  :valor1="(evento) => estado.valor1 = parseInt(evento.target.value)" :valor2="(evento) => estado.valor2 = parseInt(evento.target.value)"/>
    <Seletor :operacao="(evento) => estado.operacao = evento.target.value"/>
    <CampoResultado  :value= calcular()  />
</div>
</template>




<style scoped>
.container{
  max-width:500px;
  width: 100%;
  background-color: rgb(106, 221, 250);
  text-align: center;
}

@media screen and (max-width:767px) {
  .container {
    max-width: 100vw;
    width: 100%;
  }
}
</style>
