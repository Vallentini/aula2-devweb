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
const menor = '<div style="border-radius:20px; background-color: rgb(202, 59, 59); width: 500px; color:black; height: 30px; margin-top: 15px"><p style="margin-left:150px">maior que 10 é red</p></div>'
const maior = '<div style="border-radius:20px; background-color: green; width: 500px; color:black; height: 30px; margin-top: 15px;"><p style="margin-left:150px">menor que 10 é verdin </p></div>'
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
    <div v-if="contador > 10 " v-html="maior" ></div>
  <div v-else v-html="menor"></div>
</div>
</template>

<style scoped>

.info {
  background-color: rgb(30, 117, 98);
  padding: 20px 30px;
  color: rgb(238, 243, 245);
  border-radius: 10px;
  margin-right: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
  
}
button:hover {
    transform: scale(1.1);

}

button {
  background-color: cadetblue;
  height: 40px;
  margin-left: 10px;
  color: rgb(250, 250, 250);
  font-weight: bold;
  border-radius: 10px;
  transition: transform .2s;

}
</style>
