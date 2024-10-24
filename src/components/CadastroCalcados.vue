<template>
    <div>
      <h2>Cadastro de Calçados</h2>
      <form @submit.prevent="onSubmit">
        <div>
          <label>Nome:</label>
          <input type="text" v-model="calcado.nome" />
        </div>
        <div>
          <label>Tamanho:</label>
          <input type="number" v-model="calcado.tamanho" />
        </div>
        <div>
          <label>Preço:</label>
          <input type="number" v-model="calcado.preco" />
        </div>
        <button type="submit">Cadastrar</button>
      </form>
      <p v-if="mensagem">{{ mensagem }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        calcado: {
          nome: '',
          tamanho: null,
          preco: null,
        },
        mensagem: ''
      };
    },
    methods: {
      onSubmit() {
        this.mensagem = `Calçado cadastrado: ${this.calcado.nome}, Tamanho: ${this.calcado.tamanho}, Preço: R$${this.calcado.preco}`;
        this.resetForm();
      },
      resetForm() {
        this.calcado = { nome: '', tamanho: null, preco: null };
      }
    }
  };
  </script>
  
  <style scoped>
  div {
    margin-bottom: 10px;
  }
  </style>
  