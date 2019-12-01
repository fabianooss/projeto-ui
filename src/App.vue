<template>
  <div id="app">
    <form-projeto></form-projeto>

    <lista-projetos></lista-projetos>
    <area-total></area-total>
  </div>
</template>

<script>
import FormProjeto from '@/components/FormProjeto'
import ListaProjetos from '@/components/ListaProjetos'
import AreaTotal from '@/components/AreaTotal'

export default {
  name: 'app',
  components: {
    FormProjeto, ListaProjetos, AreaTotal
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
