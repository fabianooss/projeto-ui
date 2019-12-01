<template>
  <div>
      <button @click="listarProjetos">Ver todos projetos</button>
      <table v-if="projetos != null">
          <tr>
              <th>Nome</th>
              <th>Área</th>
              <th>Prazo</th>
              <th>Orçamento</th>
          </tr>
          <tr v-for="p in projetos" :key="p.id">
              <td>{{p.nome}}</td>
              <td>{{p.area.nome}}</td>
              <td>{{p.prazo}}</td>
              <td>{{p.orcamento}}</td>
          </tr>
      </table>
  </div>
</template>

<script>
import axios from 'axios'
export default {

    data() {
        return {
            projetos: null
        }
    },
    methods: {
        listarProjetos() {
            axios.get("http://localhost:8080/projeto").then(response =>{
                this.projetos = response.data
            })

        }
    }

}
</script>

<style>

</style>