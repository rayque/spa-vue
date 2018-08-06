<template>
<login-template>

<span slot="menuesquerdo">
<img src="https://www.oficinadanet.com.br/imagens/post/19125/social.jpg" class="responsive-img" alt="">
</span>
  
<span slot="principal">

      <h2>Cadastro</h2>
    <input type="text" placeholder="Nome" value="">
    <input type="text" placeholder="E-mail" value="">
    <input type="text" placeholder="senha" value="">
    <input type="text" placeholder="Confirme sua senha" value="">
    <button type="button" class="btn">Cadastrar</button>    
    <router-link to="/login" class="btn orange"> Já tenho conta </router-link>


</span>
  
</login-template>
</template>

<script>  
import LoginTemplate from '@/templates/LoginTemplate'

export default {
  name: 'Cadastro',
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
