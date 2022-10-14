<template>
  <div>
    <!-- 
      primeiro, um input pra atribuir nome e valor de dado. 
      depois fazer um for e analizar os valores de todo mundo, depois botar, 
  -->
  <div class="iku"></div>
    <p class="sexo">Versão 0.00000000000000000000000000000000000000000000000000000000000000000000000000000..............</p>
    <p>Nome do personagem</p>
    <input class="vitin" type="text"><br>
    <p>Dado</p>
    <input class="breno" type="number" min='1' max="20"><br><br>
    <button v-on:click="Turno()">adcionar player</button><br><br>
    <!-- um for para cada player é melhor <div id="ordem_player">{{players}}</div> -->
    <div class="resultado"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
      return {
        players: []
      }
  },
  methods:{
    // função pra botar o numero e calcular o player que vai primeiro. Mostra só o nome e o dado
    Turno(){
        var pers = document.querySelector('.vitin')
        console.log(pers)
        return pers
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button{
  padding:11px;
  border-radius: .4em;
  background:#4499aa;
}
</style>
