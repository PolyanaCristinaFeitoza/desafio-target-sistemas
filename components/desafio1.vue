<template>
    <div class="soma">
      <h2>Desafio 1: Soma</h2>
      <p>Resultado da soma: {{ soma }}</p>
    </div>
</template>
  
<script setup lang="ts">
    import { ref } from 'vue';
  
    let indice = ref<number>(13);
    let soma = ref<number>(0);
    let k = ref<number>(0);
  
    while (k.value < indice.value) {
      k.value += 1;
      soma.value += k.value;
    }
</script>

<style>
.soma {
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
