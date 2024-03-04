<script setup>
import { reactive, ref } from 'vue';

const professor = ref({
  nome: 'Eduardo da Silva',
  disciplinas: [
    'Desenvolvimento Web II',
    'Desenvolvimento de Aplicativos para Dispositivos Móveis',
  ],
});

const contador = reactive({
  contador1: 0,
  contador2: 0,
 
});

function decrementar() {
  if (contador.contador1 > 0) {
    contador.contador1--
  }
}

function decrementar1() {
  if (contador.contador2 > 0) {
    contador.contador2--
  }
}
function possuiDisciplinas() {
  return professor.value.disciplinas.length > 0;
}
</script>

<template>
  <div>
    <h1>Professor</h1>
    <p>Nome: {{ professor.nome }}</p>
    <p v-if="!possuiDisciplinas">O professor não possui disciplinas.</p>
    <div v-else>
      <p>O professor possui disciplinas.</p>
      <ul>
        <li v-for="disciplina in professor.disciplinas" :key="disciplina">
          {{ disciplina }}
        </li>
      </ul>
    </div>
  </div>

  <div>

    
    <p>{{ contador.contador1 }}</p>
    <button @click="decrementar"> - </button>
    <button @click="contador.contador1++"> + </button>


    <p>{{ contador.contador2 }}</p>
    <button @click="decrementar1"> - </button>
    <button @click="contador.contador2++"> + </button>

    <p>a soma dos dois contadores é {{ soma }}</p>
  </div>





</template>
