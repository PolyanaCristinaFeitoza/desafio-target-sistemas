<template>
    <div class="faturamento-percentual">
      <h2>Desafio 4: Percentual de Faturamento</h2>
      <div v-for="(valor, estado) in percentuais" :key="estado">
        <p>{{ estado }}: {{ valor }}%</p>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  const faturamento = {
    SP: 67836.43,
    RJ: 36678.66,
    MG: 29229.88,
    ES: 27165.48,
    Outros: 19849.53
  };
  
  const totalFaturamento = Object.values(faturamento).reduce((acc, val) => acc + val, 0);
  const percentuais = Object.keys(faturamento).reduce((acc, estado) => {
    acc[estado] = ((faturamento[estado] / totalFaturamento) * 100).toFixed(2);
    return acc;
  }, {} as Record<string, string>);
  </script>

<style>
.faturamento-percentual {
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
