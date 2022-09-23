<template>
    <div>
        <label for="nomeAluno">Nome aluno: </label>
        <input type="text" id="nomeAluno" v-model="nomeAluno" required>     <br/>
        
        <label for="notaAluno1">Nota 1: </label>
        <input type="number" id="notaAluno1" v-model="notaAluno1" required> <br/>

        <label for="notaAluno2">Nota 2: </label>
        <input type="number" id="notaAluno2" v-model="notaAluno2" required> <br/>

        <label for="notaAluno3">Nota 3: </label>
        <input type="number" id="notaAluno3" v-model="notaAluno3" required> <br/>
        
        <input type="button" value="Confirmar" @click="adicionarAluno"/>         <br/>
    
        <table>
        <tr>
            <th>Nome</th>
            <th>Situação</th>
        </tr>
        <tr v-for='item in mediaAlunos' :key="item.Situacao" id="linhaTabela"  :class="[item.Situacao]"> 
            <td>
                {{item.Nome}}
            </td>
            <td>
                {{item.Situacao}}
            </td>
        </tr>
        </table>
    </div>
</template>

<script>
export default {
    data(){
        return{
            nomeAluno: '',
            notaAluno1: 0,
            notaAluno2: 0,
            notaAluno3: 0,
            situacaoAluno: '',
            mediaAlunos: [],
        }
    },

    methods:{
        adicionarAluno(){
            if( (this.nomeAluno) && (this.notaAluno1) && (this.notaAluno2) && (this.notaAluno3) ){
                let mediaApr = (this.notaAluno1 + (this.notaAluno2 * 2) + (this.notaAluno3 * 3)) / 6
                if (mediaApr > 6.9) {
                    console.log(this.mediaAlunos.push ({Nome: this.nomeAluno, Situacao: 'Aprovado'}))
                }
                else{
                    this.mediaAlunos.push ({Nome: this.nomeAluno, Situacao: 'Reprovado'})
                }
            }  
        }
    }
}
</script>

<style>
    th, td{
        border: 1px solid black;
    }

    .Aprovado{
        background-color: rgb(0, 162, 255);
    }

    .Reprovado{
        background-color: rgb(170, 0, 0);
    }

</style>