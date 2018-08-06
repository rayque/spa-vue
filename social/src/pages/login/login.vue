<template>
<login-template>

<span slot="menuesquerdo">
<img src="https://www.oficinadanet.com.br/imagens/post/19125/social.jpg" class="responsive-img" alt="">
</span>
  
<span slot="principal">

      <h2>Login</h2>
    <input type="text" placeholder="E-mail" value="">
    <input type="text" placeholder="senha" value="">
    <button type="button" class="btn">Entrar</button>   
    <router-link to="/cadastro" class="btn orange"> Cadastre-se </router-link>

</span>
  
</login-template>
</template>

<script>  
import LoginTemplate from '@/templates/LoginTemplate'

export default {
  name: 'Login',
  props: [],
  data(){
    return{
    }
  },
  components:{
    LoginTemplate,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
