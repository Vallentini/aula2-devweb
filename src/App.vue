<script setup>
//CONTADOR
import{ref} from 'vue'
let contador = ref(0)

 function incrementar() {
    contador.value++;
  }

function decrementar(){
  if (contador.value > 0) {
      contador.value--;
    }
  }
function reiniciar(
) {
  contador.value = 0;
}
//FORMS INFORMAÇÃO
const nome = 'Vallentini'
const idade = 16

function inverter(texto) {
  return texto.split('').reverse().join('')
}

function saudacao() {
  return `Olá, ${nome}!`
}
</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }} </p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
    <hr />
    <p> Exemplo de saudação usando função</p>
    <p> {{ saudacao() }} </p>
  </div>

  <div class="info">
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <p>O valor do contador é: {{ contador }}</p>
    <button @click="reiniciar">Reiniciar</button>
  </div>
</template>

<style scoped>
.info {
  background-color: rgba(35, 12, 22, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin-right: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>
