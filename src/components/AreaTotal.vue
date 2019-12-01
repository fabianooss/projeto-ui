<template>
  <div>
      <div v-for="a in areaTotal" :key="a.area" class="projeto">
          Área: {{a.area}} <br/>
          Orçamento total: {{a.orcamentoTotal}} <br/>
          Prazo médio: {{a.prazoMedio}} <br/>
          Quantidade: {{a.quantidadeProjetos}}<br/>
      </div>

  </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            areaTotal: []
        }
    },
    mounted() {
        axios.get("http://localhost:8080/projeto/total-area").then(response=> {
            this.areaTotal = response.data
        })
    }
}
</script>

<style>
.projeto {
    border: 1px solid silver;
    padding: 5px;
}
</style>