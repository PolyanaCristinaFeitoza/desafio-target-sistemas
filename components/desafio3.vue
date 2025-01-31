<template>
    <div class="faturamento">
      <h2>Desafio 3: Faturamento</h2>
      <p>Menor Faturamento: {{ menorFaturamento }}</p>
      <p>Maior Faturamento: {{ maiorFaturamento }}</p>
      <p>Dias Acima da Média: {{ diasAcimaDaMedia }}</p>
    </div>
</template>
  
<script setup lang="ts">
  import faturamento from '../assets/faturamento.json';
  
  const valores = faturamento.filter((dia: any) => dia.value > 0).map((dia: any) => dia.value);
  
  const menorFaturamento = Math.min(...valores);
  const maiorFaturamento = Math.max(...valores);
  const mediaFaturamento = valores.reduce((acc: number, val: number) => acc + val, 0) / valores.length;
  
  const diasAcimaDaMedia = valores.filter((value: number) => value > mediaFaturamento).length;
  </script>

<style>
.faturamento {
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>