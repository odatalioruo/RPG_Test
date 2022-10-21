<template>
  <div>
    <!-- 
      primeiro, um input pra atribuir nome e valor de dado. 
      depois fazer um for e analizar os valores de todo mundo, depois botar, 
  -->
  <div class="iku"></div>
    <p id="sexo">Versão 0...............</p>
    <p>insira texto</p>
    <input id="vitin" type="text"><br>
    <p>Valor</p>
    <input id="breno" type="number" min='1' max="20"><br><br>
    <button v-on:click="Turno()">adcionar</button><br><br>
    <!-- um for para cada player é melhor <div id="ordem_player">{{players}}</div> -->
    <p id="resultado"></p>
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
        numbers: [],
        rest: []
      }
  },
  methods:{
    // eu faço o sort dos numeros daí eu faço ifs que se o nome for igual a o numero ele bota na ordem do sort
    Turno(){
        var resultado = document.querySelector('#resultado')//seleciona a div res
        var pers = document.querySelector('#vitin').value;// seleciona o input pers
        var dado = document.querySelector('#breno').value;//seleciona o input dado
        this.players.push([pers, dado])// bota os valores de dado e personagem no players
        this.numbers.push(dado)// bota os valores de dado no numbers
      //  console.log(this.players) // log
        resultado.innerHTML = ''; // limpa o resultado
       // console.log(this.players[0][1]) // log
        resultado.append('kk    ') // mensagem se nada acontecer com resultado
        //console.log(this.players.length)
        this.rest = []
        if (this.players.length === 1){ //único player
          return resultado.append(this.players)
        } else {
            // -- sorting the numbers --  \\
          this.numbers.sort(function(a,b){
                   return a - b
          })
          this.numbers.reverse()
          
          for(let i = 0; i<this.players.length; i++){
            for(let j = 0; j < this.players.length; j++){

            if(this.players[j][1] == this.numbers[i]){
                this.rest.push(this.players[j][0])
            } 
   }
    
}
      resultado.append(this.rest)

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
