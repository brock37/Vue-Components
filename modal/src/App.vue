<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <button type="submit" @click="showModal = true">show modal</button>
    <ModalBox v-if="showModal" @close="showModal = false">
      <span slot="header">My custom header</span>
      <div slot="body">
        <input type="text" name="mytest" v-model="test">  
        <button @click="valid">Valid</button>
      </div>
    </ModalBox>
  </div>
</template>

<script>
import  ModalBox  from "./components/ModalBox";
export default {
  name: 'App',
  components: {
    ModalBox
  },
  data (){
    return {
      showModal : false,
      test : "Savoir si la gestion du body peux venir de l'exterieur"
    }
  },
  methods:{
    valid(){
      alert("Sa marche")
    }
  }
}
</script>

<style>
h3{
  margin: 0;
}

</style>
