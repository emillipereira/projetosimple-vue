<template>
  <v-containte class="pa-8" fluid>
    <h1 class="h1">My to-do list</h1>
    <v-form>
      <v-text-field 
        label="Nova tarefa" 
        v-model="novaTarefa" 
        @keydown.enter="adicionar"
      >
        <v-icon slot="append" @click="adicionar">mdi-send</v-icon>
      </v-text-field>
    </v-form>
    <v-divider></v-divider>
    <v-list>
      <v-list-item-group>
        <v-list-item v-for="tarefa of tarefas" :key="tarefa.titulo">
          {{tarefa.titulo}}
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-containte>
</template>

<script>
export default {
  data() {
    return {
      novaTarefa: '',
      tarefas: [
        {titulo: "Tarefa A"},
        {titulo: "Tarefa B"},
        {titulo: "Tarefa C"},
      ],
    };
  },
  methods: {
    adicionar(e) {
      e.preventDefault();
      this.tarefas.push({titulo: this.novaTarefa});
      this.novaTarefa = "";
    },
  },
};
</script>

<style>
</style>