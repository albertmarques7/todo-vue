<script setup>
  const props = defineProps(['tarefas']);
</script>
<!-- fazer um v-if para aparecer ul se for maior que 0 tarefas, se não. escrever não há tarefas -->
<template> 
    <ul v-if="tarefas.length > 0" class="list-group mt-4">
  <li class="list-group-item" v-for="tarefa in props.tarefas">
    <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
    <label :class="{done: tarefa.finalizada ===true}" class="ms-3" :for="tarefa.titulo">
      {{tarefa.titulo}}
    </label>
  </li>
</ul>
<h3 v-else>Não há tarefas</h3>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>
