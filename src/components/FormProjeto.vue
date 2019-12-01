<template>
   <div>
       <form @submit.prevent="salvar">
            Nome:
            <input type="text" v-model="projeto.nome" required autofocus/>
            <br/>

            Área:
            <select v-model="projeto.area">
                <option v-for="a in areas" :key="a.id" :value="a">
                    {{a.nome}}
                </option>
            </select>

            <br/>
            Prazo:
            <input type="number" v-model="projeto.prazo" required/>
            <br/>

            Orçamento:
            <input type="number" step="0.01" v-model="projeto.orcamento" required/>

            <br/>

            <input type="submit" value="Salvar"/>

       </form>
   </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            projeto: {
                nome: null,
                area: null,
                prazo: null,
                orcamento: null
            },
            areas: []
        }
    },
    mounted() {
        axios.get("http://localhost:8080/area").then(response => {
            this.areas = response.data
        })
    },
    methods: {
        salvar() {
            axios.post("http://localhost:8080/projeto", this.projeto).then(response => {
                this.projeto = response.data
                alert('Projeto cadastrado')
            }).catch(error => {
                alert(error.response)
            })
        }
    }

}
</script>

<style>

</style>