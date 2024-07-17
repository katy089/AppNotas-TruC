<template>
  <h2>Mis Notas</h2> 
  <CreateNote v-on:SeDataToCnote="CreateNote"/>
  <ListNote v-bind:notesd="notes"/>
</template>

<script>
import CreateNote from './components/create-notes.vue';
import ListNote from './components/ListNotes.vue';

export default {
  name: 'App',
  components:{
    CreateNote,
    ListNote,
  },
  data(){
    return{
       notes:[
        {
           title:"Nota 1",
           description:"Mi primera nota",
        },{
           title:"Nota 2",
           description:"Esta es una nota larga que ocupa más de una línea",
        },{
           title:"Nota 3",
           description:"Otra nota de ejemplo",
        },{
           title:"Nota 4",
           description:"Última nota de ejemplo",

        }],
     }
  },
  methods:{
    CreateNote(note){
      this.notes.push(note);
      alert("Note added");
    }
  }
}
</script>

<style>
#app {
  font-family: Roboto sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: gray;
  margin-top: 60px;
  
}
</style>
