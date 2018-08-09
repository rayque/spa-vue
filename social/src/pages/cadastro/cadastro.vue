<template>
<login-template>

<span slot="menuesquerdo">
<img src="https://www.oficinadanet.com.br/imagens/post/19125/social.jpg" class="responsive-img" alt="">
</span>
  
<span slot="principal">

      <h2>Cadastro</h2>
    <input type="text" placeholder="Nome" v-model="name">
    <input type="text" placeholder="E-mail" v-model="email">
    <input type="password" placeholder="senha" v-model="password">
    <input type="password" placeholder="Confirme sua senha" v-model="password_confirmation">
    <button type="button" class="btn" v-on:click="cadastro()">Cadastrar</button>    
    <router-link to="/login" class="btn orange"> Já tenho conta </router-link>


</span>
  
</login-template>
</template>

<script>  
import LoginTemplate from '@/templates/LoginTemplate'
import axios from  'axios'

export default {
  name: 'Cadastro',
  props: [],
  data(){
    return{ 
      name:'',
      email:'',
      password:'',
      password_confirmation:'',
    }
  },
  components:{
    LoginTemplate,
  },
    methods:{
    cadastro(){
      axios.post('http://localhost:8000/api/cadastro', {
        name: this.name,
        email: this.email,
        password: this.password,
        password_confirmation: this.password_confirmation, 
      })
      .then(response => {
         if (response.data.token) {
           console.log("Success register!");           
           sessionStorage.setItem('usuario', JSON.stringify(response.data));
           this.$router.push('/');
         } else if (response.data.status == false) {
           alert("regitration error!");
         } else {
           console.log("Validation errors!");
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
