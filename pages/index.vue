<template>
    <div class="content-index">
      <h1>DESAFIO TARGET</h1>

      <div class="buttons">
        <button @click="setActiveChallenge('desafio-1')">Desafio 1: Soma</button>
        <button @click="setActiveChallenge('desafio-2')">Desafio 2: Fibonacci</button>
        <button @click="setActiveChallenge('desafio-3')">Desafio 3: Faturamento</button>
        <button @click="setActiveChallenge('desafio-4')">Desafio 4: Percentual</button>
        <button @click="setActiveChallenge('desafio-5')">Desafio 5: Reverso</button>
      </div>

      <div v-if="activeChallenge === 'desafio-1'">
        <Desafio1 />
      </div>
      <div v-if="activeChallenge === 'desafio-2'">
       <Desafio2 />
      </div>
      <div v-if="activeChallenge === 'desafio-3'">
        <Desafio3 />
      </div>
      <div v-if="activeChallenge === 'desafio-4'">
        <Desafio4 />
      </div>
      <div v-if="activeChallenge === 'desafio-5'">
       <Desafio5 />
      </div>
    </div>
</template>
  
 <script setup lang="ts">
    import { ref } from 'vue';
    import Desafio1 from '../components/desafio1.vue'
    import Desafio2 from '../components/desafio2.vue'
    import Desafio3 from '../components/desafio3.vue'
    import Desafio4 from '../components/desafio4.vue'
    import Desafio5 from '../components/desafio5.vue'

    const activeChallenge = ref<string | null>(null);

    const setActiveChallenge = (challenge: string) => {
        activeChallenge.value = challenge;
    };
</script>

<style>
.content-index {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 16px;
}

.buttons {
  display: flex;
  gap: 12px;
  width: 100%;

  button {
    background: #b33516;
    border: none;
    border-radius: 12px;
    color: #fff;
    height: 40px;
    width: 100%;
  }
}
</style>
  