<template>
    <div class="reverso">
      <h2>Desafio 5: Reverso</h2>
      <input class="input-reverso" v-model="texto" placeholder="Digite uma string" />
      <button class="button-reverso" @click="inverterTexto">Inverter Texto</button>
      <p>{{ textoInvertido }}</p>
    </div>
</template>
  
<script setup lang="ts">
  import { ref } from 'vue';
  
  const texto = ref<string>();
  const textoInvertido = ref<string>("");
  
  const inverterTexto = () => {
    let textoOriginal = texto.value;
    let invertido = '';
    if (textoOriginal) {
        for (let i = textoOriginal.length - 1; i >= 0; i--) {
          invertido += textoOriginal[i];
        }
        textoInvertido.value = invertido;
    }
  };
</script>

<style>
.reverso {
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.input-reverso {
  border: 1px solid #b33516;
  border-radius: 8px;
  height: 30px;
  margin: 0 0 12px;
}
.button-reverso {
  color: #fff;
  border: none;
  height: 30px;
  border-radius: 8px;
  width: 100px;
  background: #b33516;
}
</style>
