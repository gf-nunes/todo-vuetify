<template>
  <div>
    <v-col
      cols="12"
     >
     <v-text-field
      v-model="campoInput"
      label="Incluir Tarefa"
      outlined
      clearable
      @keyup.enter="handleAddTarefa"
     >
     </v-text-field>
    </v-col>
    <v-list
      flat
      subheader
    >
      <v-list-item-group
        multiple
        active-class=""
      >

      <div
      v-for="tarefa, index in tarefas"
      :key="index"
      >
        <TarefaList 
        :tarefa="tarefa"
        />
      </div>

      </v-list-item-group>
    </v-list>
  </div>
</template>

<script>
  import TarefaList from '../components/tarefas/TarefaList.vue'

  export default {
    name: 'TarefasView',

    components: {
      TarefaList
    },
    data () {
      return{
        campoInput: null,
        tarefas:[
          {titulo: "Ir ao mercado", concluido: false},
       ]
      }
    },
    methods: {
      handleAddTarefa() {
        if(this.campoInput){
          this.tarefas.push({
            titulo:this.campoInput,
            concluido: false
          })
          this.campoInput = null;
        }
      }
    }
  }
</script>
