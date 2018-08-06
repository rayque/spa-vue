<template>
  <footer>
    <div :class="cor">

      <div class="container">
        <div class="row">
          <div class="col l6 s12">
            <h5 class="white-text">{{ logo || 'Site' }}</h5>
            <p class="grey-text text-lighten-4">{{ descricao || 'Coloque aqui sua descrição ' }}</p>
          </div>
          <div class="col l4 offset-l2 s12">
            <h5 class="white-text">Links</h5>
            <ul>
              <li><a class="grey-text text-lighten-3" href="#!">Link 1</a></li>
              <li><a class="grey-text text-lighten-3" href="#!">Link 2</a></li>
              <li><a class="grey-text text-lighten-3" href="#!">Link 3</a></li>
              <li><a class="grey-text text-lighten-3" href="#!">Link 4</a></li>
            </ul>
          </div>
        </div>
      </div>
      <div class="footer-copyright">
        <div class="container">
          © {{ano || '2018'}} Copyright Text
        </div>
      </div>
    </div>
  </footer>

</template>

<script>
export default {
  name: 'FooterVue',
  props: ['logo', 'descricao', 'cor', 'ano'],
  data(){
    return{

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
