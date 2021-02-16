<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <Cliente :cliente="clienteMich" :showIdade="true"/>
    <Cliente :cliente="clienteNicky" :showIdade="true"/>
    <Cliente :cliente="clienteHarder" :showIdade="false"/>
    <Cliente :cliente="clienteJuh" :showIdade="false"/>
  </div>
</template>

<script>

import Cliente from './components/Cliente'

export default {
  name: 'App',
  data() {
    return {
      clienteMich: {
        nome: 'Michel França',
        email: 'mich@gmail.com',
        idade: 19
      },
      clienteNicky: {
          nome: 'Nicole Cristyne',
          email: 'nicky@gmail.com',
          idade: 18
      },
      clienteHarder: {
          nome: 'Júlia Harder',
          email: 'harder@gmail.com',
          idade: 17
      },
      clienteJuh: {
          nome: 'Júlia Roberta',
          email: 'juh@gmail.com',
          idade: 17
      }
    }
  },
  components: {
    Cliente,
  }
}
</script>

<style>
</style>