
<script setup>
import { reactive } from 'vue';
  const estado = reactive({
    saldo: 5000,
    transferindo: 0,
    nomes: ["gui","gabriel","eduardo","gg"],
    nomeInserir: '',
  });

  function saldoFuturo() {
    const {saldo,transferindo} = estado;
    if ((saldo-transferindo) >= 0) {
      return saldo - transferindo;
    } else {
      return "Saldo insuficiente"
    }
  }

  function cadastraNome() {
    estado.nomes.push(estado.nomeInserir)
  }





</script>

<template>
  <br>
  <hr>
  <div class="banco">
    <h2>Saldo: {{ estado.saldo }}.</h2>
    <h3>Transferindo: {{ estado.transferindo }}</h3>
    <h3>Saldo após a tranferencia: {{ saldoFuturo() }}</h3>
    <input :class="{ invalido: estado.transferindo > estado.saldo }" @keyup="evento => estado.transferindo = evento.target.value" type="number" placeholder="Quantia para transferir">
  </div>
  <br>
  <hr>
  <ul>
    <li v-for="nome in estado.nomes">
      {{ nome }}
    </li>
  </ul>
  <input @keyup="evento => estado.nomeInserir = evento.target.value" type="text" placeholder="Digite um novo nome:">
  <button @click="cadastraNome()" type="button">Cadastrar</button>
</template>

<style scoped>
  .invalido {
    border-color: red;
    outline-color: red;
  }
  .banco {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    .sub {
      margin-top: 16px;
    }
  }
</style>
