<template>
<site-template>
  <span slot="menuesquerdo">
    <div class="row valign-wrapper">
      <grid-vue tamanho="4">
        <img src="https://materializecss.com/images/yuna.jpg" alt="" class="circle responsive-img">
      </grid-vue>
      <grid-vue tamanho="8">
        <span class="black-text">
          <h5>Maria</h5>
          This is a square image. Add the "circle" class to it to make it appear circular.
        </span>
      </grid-vue>
    </div>
  </span>
  <publicar-conteudo-vue/>

<span slot="principal">
    <card-conteudo-vue
    perfil="https://materializecss.com/images/yuna.jpg"
    nome="Maria Silva"
    data="22/06/2018 11:44"
    >
    <card-detalhe-vue
    img="https://materializecss.com/images/sample-1.jpg"
    titulo="Título do cartão"
    txt="Texto do card skabcksjd sdkvj sdkjlvsdk vs assadsafdfasfjfkljdfiosdflksdj "/>

  </card-conteudo-vue>
</span>

</site-template>
</template>

<script>
import SiteTemplate from '@/templates/SiteTemplate'
import CardConteudoVue from '@/components/social/CardConteudoVue'
import CardDetalheVue from '@/components/social/CardDetalheVue'
import PublicarConteudoVue from '@/components/social/PublicarConteudoVue'

export default {
  name: 'Home',
  props: [],
  data(){
    return{

    }
  },
  components:{
    SiteTemplate,
    CardConteudoVue,
    CardDetalheVue,
    PublicarConteudoVue,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
