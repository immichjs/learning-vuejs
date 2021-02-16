<template>
  <div id="app">
    <h3>Cadastrar Clientes</h3>
    <small class="nome-erro" v-show="onError">O nome é inválido, tente novamente</small><br>
    <input type="text" placeholder="nome" v-model="nomeField">
    <input type="email" placeholder="email" v-model="emailField">
    <input type="number" placeholder="idade" v-model="idadeField">
    <button @click="cadastrarUsuario">Cadastrar</button>

    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h1>{{ index + 1 }}</h1>
      <Cliente :cliente="cliente"/>
    </div>
  </div>
</template>

<script>

import Cliente from './components/Cliente'

export default {
  name: 'App',
  data() {
    return {
      onError: false,
      nomeField: '',
      emailField: '',
      idadeField: 0,
      clientes: [
        {
          id: 1,
          nome: 'Michel França',
          email: 'mich@gmail.com',
          idade: 19
        },
        {
          id: 2,
          nome: 'Nicole Cristyne',
          email: 'nicky@gmail.com',
          idade: 18
        },
        {
          id: 3,
          nome: 'Júlia Harder',
          email: 'harder@gmail.com',
          idade: 17
        },
        {
          id: 4,
          nome: 'Júlia Roberta',
          email: 'juh@gmail.com',
          idade: 17
        },
      ]
    }
  },
  components: {
    Cliente
  },
  methods: {
    cadastrarUsuario() {
      if (this.nomeField == '' || this.nomeField == ' ' || this.nomeField.length < 3) {
        this.onError = true
        console.log('Erro de validação')
      } else {
        this.clientes.push({ nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now() })
        this.nomeField = ''
        this.emailField = ''
        this.idadeField = ''
        this.onError = false
      }
    }
  }
}
</script>

<style>
  .input-text {
    padding: 10px;
    margin-right: 5px;
  }

  .nome-erro {
    color: lightcoral;
  }
</style>