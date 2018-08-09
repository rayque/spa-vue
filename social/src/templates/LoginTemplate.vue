<template>
  <span>
    <header>
      <nav-bar cor="green darken-1" logo="Social" url="/">
        <li><router-link to="/">Home</router-link></li>
        <li v-if="!usuario" ><router-link to="/cadastro">Cadastre-se</router-link></li>
        <li v-if="usuario" ><router-link to="/perfil">{{ usuario.name }}</router-link></li>
        <li v-if="usuario" ><a v-on:click="sair()">Sair</a></li>
      </nav-bar>
    </header>

    <main>
      <div class="container">        
        <div class="row">

          <grid-vue tamanho="8">
            <slot name="menuesquerdo" />
          </grid-vue>

          <grid-vue tamanho="4">
            <slot name="principal" />
          </grid-vue>

        </div>
      </div>
    </main>

    <footer-vue cor="blue darken-1" logo="Social" descricao="Descricao do site" ano="2018"/>



  </span>
</template>

<script>
import NavBar from '@/components/layouts/NavBar'
import FooterVue from '@/components/layouts/FooterVue'
import GridVue from '@/components/layouts/GridVue'
import CardMenuVue from '@/components/layouts/CardMenuVue'

export default {
  name: 'LoginTemplate',
    data(){
      return {
        usuario: false
      }
    },
  components:{
    NavBar,
    FooterVue,
    GridVue,
    CardMenuVue,
  },
  created(){
    let usuarioAux = sessionStorage.getItem('usuario');
    if (usuarioAux) {
      this.usuario = JSON.parse(usuarioAux); 
      this.$router.push('/login');
    }    
  }, 
  methods:{
    sair(){
      sessionStorage.clear();
      this.usuario = false;    
      this.$router.push('/login');
    }
  },
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
