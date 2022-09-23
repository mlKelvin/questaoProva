<template>
  <div>
    <aluno-media></aluno-media>
  </div>
</template>

<script>
//import alunomedia from './components/alunomedia.vue'
import AlunoMedia from './components/AlunoMedia.vue'

export default {

  components: {
    AlunoMedia,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
