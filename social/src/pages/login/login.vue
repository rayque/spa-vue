<template>
<login-template>

<span slot="menuesquerdo">
<img src="https://www.oficinadanet.com.br/imagens/post/19125/social.jpg" class="responsive-img" alt="">
</span>
  
<span slot="principal">

    <h2>Login</h2>
    <input type="text" placeholder="E-mail" v-model="email">
    <input type="password" placeholder="senha" v-model="password">
    <button type="button" class="btn" v-on:click="login()">Entrar</button>   
    
    <router-link to="/cadastro" class="btn orange"> Cadastre-se </router-link>

</span>
  
</login-template>
</template>

<script>  
import LoginTemplate from '@/templates/LoginTemplate'
import axios from 'axios'

export default {
  name: 'Login',
  props: [],
  data(){
    return{
      email:'',
      password:'',
    }
  },
  components:{
    LoginTemplate,
    axios,
  },
  methods:{
    login(){
      axios.post('http://localhost:8000/api/login', {
        email:this.email,
        password:this.password,
      })
      .then(response => {
         if (response.data.token) {
           sessionStorage.setItem('usuario', JSON.stringify(response.data));
           this.$router.push('/');
         } else if (response.data.status == false) {
           console.log("Login does not exist!");
           alert("Login does not exist!");
         } else {
           console.log("Validation erros!");
           let erros = '';
           for (let erro of Object.values(response.data)) {
             erros +=  erro +=" ";              
           }
           alert(erros);
         }
      })
      .catch(e => {
        console.log(e);
        alert("Error! Please, Try again later.");

      })
        
    }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
