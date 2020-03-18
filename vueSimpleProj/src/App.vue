<template>
  <div class="container outer">
    <div class="row">
     
      <div class="col-xs-12 col-sm-12">
          <app-bar :prg="dataOfNotes.length"></app-bar>
      </div>
    </div>
      <div>
          <app-home  :add="addNote"></app-home>
      </div>
      <div>
          <app-notes :data="dataOfNotes" :remove="removeNote"></app-notes>
      </div>
    
    <footer>
      <h4>By Aashish Peepra</h4>
    </footer>
  </div>
</template>

<script>
import Bar from './Components/Bars';
import Home from './Components/Home';
import Notes from './Components/Notes';
export default {
  data:function(){
    return {
      dataOfNotes:["Notes Will Appear Here"]
    }
  },
  components:{
    appBar:Bar,
    appHome:Home,
    appNotes:Notes
  },
  methods:{
    removeNote(index){
      this.dataOfNotes.splice(index,1);
    },
    addNote(value){
      if(this.dataOfNotes.length<10)
      {
        this.dataOfNotes.push(value);
      }
      else{
        alert("Free Some Space First");
      }
      
    }
  }
}
</script>

<style  >
  .outer{
    margin:20px auto;
  }
  h2{
    font-family: 'Righteous', cursive;
    color:#6a6a6a;
  }  
  footer{
    bottom:0;
    text-align: right;
    color:#afafaf;
  }
</style>
