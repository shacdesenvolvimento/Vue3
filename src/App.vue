<template>
  <TheHeader v-if="Showreader" />
  <img alt="Vue logo" src="./assets/logo.png">
<!--v-show similar if porem não tem else
v-for é o loop do Vue
-->
  <div v-show="ShowName">
    {{ FirstName }} <br>
    {{ LastName }}
  </div>
  <div v-if="acesso=='admin'">Admin</div>
  <div v-else-if="acesso=='marketing'">Marketing</div>
  <div v-else>User</div>
<!--
v-for é o loop do Vue
-->
  <div 
  v-for="(dados, index) in todos"
  v-bind:key="dados.id"
  class="para"
  >
  {{index}}  {{ dados.firstname }}
    
  </div>

  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
//aqui estao os componentes importados que serão utilizados neste componetes
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue'
export default {
  name: 'App',
  components: {
    //aqui estão as declarações dos componentes importados para que sejão reconhecidos
    HelloWorld,
    TheHeader
  },
  //data são todas as variaveis e objetos que serão utilizado no componente. Literlamente os dados
  data() {
    return {
      Showreader: true,
      FirstName: 'John',
      LastName: 'Doe',
      ShowName:false,
      acesso: 'marketing',
      todos:[
      {"id":1,"firstname":"John","lastname":"Doe","email":"johndoe@example.com"},
      {"id":2,"firstname":"Jane","lastname":"Smith","email":"janesmith@example.com"},
      {"id":3,"firstname":"Bob","lastname":"Johnson","email":"bobjohnson@example.com"},
      {"id":4,"firstname":"Emily","lastname":"Davis","email":"emilydavis@example.com"},
      ]

    }
  },
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
.para {
  margin: 60px;
  background-color: blue;
  color: antiquewhite;

}
</style>
