<template>
  <div>
    <!-- 
      primeiro, um input pra atribuir nome e valor de dado. 
      depois fazer um for e analizar os valores de todo mundo, depois botar, 
  -->
  <div class="iku"></div>
    <p id="sexo">Versão 0.0000000000000000000000000000000000000000000000000000000000000..............</p>
    <p>insira texto</p>
    <input id="vitin" type="text"><br>
    <p>Dado</p>
    <input id="breno" type="number" min='1' max="20"><br><br>
    <button v-on:click="Turno()">adcionar player</button><br><br>
    <!-- um for para cada player é melhor <div id="ordem_player">{{players}}</div> -->
    <p id="resultado">a</p>
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
        players: [],
        rest: []
      }
  },
  methods:{
    // função pra botar o numero e calcular o player que vai primeiro. Mostra só o nome e o dado

    Turno(){
        var resultado = document.querySelector('#resultado')
        var pers = document.querySelector('#vitin').value;
        var dado = document.querySelector('#breno').value;
        this.players.push([pers,dado])
        console.log(this.players)
        resultado.innerHTML = '';
      for(let i = 0;i<this.players.length;i++){
        resultado.append((i+1)+' - '+this.players[i][0]+'');
        resultado.append('\n')  
      }
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button{
  padding:11px;
  border-radius: .4em;
  background:#7aaabb;
}
</style>
