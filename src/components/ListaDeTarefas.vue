<script setup>
const props = defineProps(["tarefas"]);
</script>

<template>
  <ul v-if="tarefas.length > 0" class="list-group mt-4">
    <li class="list-group-item" v-for="tarefa in props.tarefas">
      <input
        @change="(event) => (tarefa.finalizada = event.target.checked)"
        :checked="tarefa.finalizada"
        :id="tarefa.titulo"
        type="checkbox"
      />
      <label
        :class="{ done: tarefa.finalizada }"
        class="ms-3"
        :for="tarefa.titulo"
        >{{ tarefa.titulo }}</label
      >
    </li>
  </ul>
  <p class="ms-2 mt-4 textcolor" v-else>Não existe Tarefas pendentes</p>
</template>
<style scoped>
.done {
  text-decoration: line-through;
}
.textcolor {
  color: green;
}
</style>
