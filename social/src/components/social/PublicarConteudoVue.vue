<template>
  <div class="row">
    <grid-vue tamanho="12" class="input-field">
      <textarea v-model="conteudo" id="textarea1" class="materialize-textarea"></textarea>
      <label for="textarea1">O que está acontecendo?</label>
    </grid-vue>
    <p>
      <grid-vue v-if="conteudo" class="btn waves-effect waves-light" tamanho="3 offset-s9">Publicar</grid-vue>
    </p>
  </div>

  </template>

  <script>
  import GridVue from '@/components/layouts/GridVue'

  export default {
    name: 'PublicarConteudoVue',
    props: [],
    data(){
      return{
        conteudo: '',
      }
    },
    components:{
      GridVue
    }
  }
  </script>

  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  </style>
