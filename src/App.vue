<script setup>
import { reactive } from 'vue'
const obj = reactive({
  n1:0,
  n2:0,
  op:'Ad'
})
const result = () =>{
  const { op } = obj;
  switch(op){
    case 'Ad':
      return (obj.n1 + obj.n2)
    case 'Sub':
      return (obj.n1 - obj.n2)
    case 'Mult':
      return (obj.n1 * obj.n2)
    case 'Div':
      return (obj.n1 / obj.n2)
    case 'Pot':
    return (obj.n1 ** obj.n2)
    case 'Rad':
    return (obj.n1 ** ( 1 / obj.n2))
      
  }
}
</script>

<template>
  <div class="container">
    <h1>Calculadora Aritmética</h1>
    <input type="number" v-model="obj.n1">
    <h2 class="container-result">Resultado: {{ result() }}</h2>
    <input type="number" v-model="obj.n2">
    <h2>Tipo de operação</h2>
    <select @change="evt => obj.op = evt.target.value"> 
      <option value="Ad">Adição</option>
      <option value="Sub">Subtração</option>
      <option value="Mult">Multiplicação</option>
      <option value="Div">Divisão</option>
      <option value="Pot">Potenciação</option>
      <option value="Rad">Radiciação</option>
    </select>
  </div>
</template>

<style scoped>
  .container{
    display: flex;
    width: 38%;
    flex-direction: column;
    align-items: center;
    margin: 2vw auto 0 auto;
  }
  h1{
    font-size: 4em;
  }
  h2{
    font-size: 2em;
    font-family: monospace;
  }
  input{
    width: 80%;
    font-size: 1.8em;
    height: 40px;
    margin: 1vw 0 ;
    border-radius: 10px;
  }
  .container-result{
    align-self: flex-start;
    margin-left: 3.5vw;
  }
  select{
    width: 30%;
    height: 40px;
    text-align: center;
    border-radius: 10px;
    font-size: 1.8em;
  }
</style>
