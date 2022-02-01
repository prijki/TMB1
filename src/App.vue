<template>
<section>
  <cabecalho/>
    <div id="titulo" class="container">
      <h1> Calculadora de Taxa de Metabolismo Basal </h1>
        <label id="sub"> Preencha com seus dados para calcular a quantidade de calorias necessárias em seu corpo.</label>
      <div class="row">
      <form id="conteudo" class="form-control">
        <br>
        <label class="form-label">Idade:</label>
        <input id="Idade" class="form-control" v-model="idade">
        <span class="input-group-btn"></span>
        <br>

        <label class="form-label">Altura:</label>
            <input id="altura" class="form-control" placeholder="cm" v-model="altura">
            <span class="input-group-btn"></span>
            <br>

        <label class="form-label">Peso:</label>
          <input id="Peso" class="form-control" placeholder="kg" v-model="peso">
          <span class="input-group-btn"></span>
        <br>
        <br>
      </form>
      Sua quantidade de calorias necessárias para homem é: {{calculoh()}} <br>
      Sua quantidade de calorias necessárias para mulher é: {{calculom()}}
      </div>
    </div>
  <rodapé/>
</section>
</template>

<script>
import cabecalho from "@/components/cabecalho"
import rodapé from "@/components/rodapé"
export default {
  name: 'App',
  components: {cabecalho, rodapé},
  data() {
    return {
      idade: '',
      altura: '',
      peso: ''
    }
  },
  methods: {
    calculoh() {
      if (this.idade, this.altura, this.peso == "")
      return 0
      else 
      return Math.round((13.8 * this.peso) + (5 * this.altura) - (6.8 * this.idade)+ 66)
    },
    calculom(){
      if (this.idade, this.altura, this.peso == "")
      return 0
      else {
      return Math.round((9.6 * this.peso) + (1.8 * this.altura) - (4.7 * this.idade) + 655)}
    },
  }
}


</script>

<style>

#titulo {
    text-align: center;
    font-family: initial;
    margin: 60px;
}

#sub {
    text-align: center;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 20px;
}
#conteudo{
    text-align: center;
}

.form-label{
    text-align: center;
    font-family: initial;
    font-size: 20px;
}
h1{
  font-size: 50px;
}

</style>
