<script setup>
import { ref } from 'vue';

const name = ref('Bokorni');
const age = ref(16);
const contador = ref(0);

function aumentar() {
  contador.value++;
}

function diminuir() {
  if (contador.value > 0) {
    contador.value--;
  }
}

function reset() {
  contador.value = 0;
}

function inverter(txt) {
  return txt.split('').reverse().join('').toUpperCase();
}

</script>

<template>
  <main>
    <h2>Informações</h2>
    <div class="quadro">

      <p>Nome: {{ name }} </p>
      <p>Idade: {{ age }} anos</p>

      <p>
        Faltam {{ 50 - age }} anos para completar 50 anos
      </p>
      <p>Este nome tem: {{ name.length }} caracteres</p>
      <p>
        Este é o nome invertido com letras maiúsculas: {{
          inverter(name) }}
      </p>
    </div>
    <div class="contador">
      <h2>Contador</h2>
      <p>Valor: {{ contador }} </p>
      <button @click="aumentar">Aumentar</button>
      <button @click="diminuir">Diminuir</button>
      <button @click="reset">Reiniciar</button>
      <div :style="{ backgroundColor: contador > 10 ? '#0F6617' : '#A30A0A' }">
        <p v-if="contador > 10">Valor maior que 10</p>
        <p v-else>Valor menor que 10</p>
      </div>
    </div>
  </main>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Amarante&display=swap');

:root {

  --fonte: "Amarante", serif;

}


.quadro,
.contador {
  background: rgb(2, 0, 36);
  background: radial-gradient(circle, rgba(2, 0, 36, 1) 0%, rgba(201, 0, 255, 1) 100%, rgba(0, 212, 255, 1) 100%);
  padding: 20px 30px;
  color: rgb(252, 252, 252);
  border-radius: 10px;


}

p {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h2 {
  color: rgb(255, 255, 255);
  font-weight: bold;
  font-size: 1.5em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

}

button {
  margin: 10px;
  padding: 10px;
  border: 0;
  border-radius: 5px;
  background: rgb(2, 0, 36);
  
  color: rgb(255, 255, 255);
  font-weight: bold;
  cursor: pointer;
  margin-left: 35px;
}

button:hover {
  transform: scale(0.9);
}
 
div {
  margin: 10px 0;
  padding: 10px;
  border-radius: 35px;
  color: white;
  font-weight: bold;
}
 
</style>