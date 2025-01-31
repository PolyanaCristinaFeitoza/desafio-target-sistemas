<template>
  <div class="fibonacci">
    <h2>Desafio 2: Fibonacci</h2>
    <input class="input-fibonacci" v-model.number="numero" placeholder="Digite um número" />
    <button class="button-verify" @click="verificarFibonacci">Verificar</button>
    <p>{{ resultado }}</p>
  </div>
</template>
  
<script setup lang="ts">
  import { ref } from 'vue';
  
  const numero = ref<number>(0);
  const resultado = ref<string>("");

  const verificarFibonacci = () => {
    const n = numero.value;
    
    if (n < 0) {
      resultado.value = "O número NÃO pertence à sequência de Fibonacci.";
      return;
    }
    
    if (n === 0 || n === 1) {
      resultado.value = "O número pertence à sequência de Fibonacci.";
      return;
    }
    
    let a = 0;
    let b = 1;

    while (b < n) {
      const temp = a;
      a = b;
      b = temp + b;
    }
    
    if (b === n) {
      resultado.value = "O número pertence à sequência de Fibonacci.";
    } else {
      resultado.value = "O número NÃO pertence à sequência de Fibonacci.";
    }
  };
</script>

<style>
.fibonacci {
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.input-fibonacci {
  border: 1px solid #b33516;
  border-radius: 8px;
  height: 30px;
  margin: 0 0 12px;
}
.button-verify {
  color: #fff;
  border: none;
  height: 30px;
  border-radius: 8px;
  width: 80px;
  background: #b33516;
}
</style>
