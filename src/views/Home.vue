<template>
  <div class="home">
    <h1> Identicon Generator </h1>
    <label>Input: </label>
    <input v-on:input="onInput"/>
    <div class="icon" v-html="identicon" />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import jdenticon from 'jdenticon'
export default {
  name: "home",
  data() {
    return {
      textInputed: ""
    }
  },
  computed:{
    identicon: function(){
      return jdenticon.toSvg(this.textInputed,400);
    }
  },
  methods:{
    onInput:function(event){
      this.textInputed = event.target.value;
    }
  }
};
</script>

<style>
h1{
  font-size:3em;
  text-shadow: 1px -1px 0 gray;
}
label{
  font-size:2em;
}
input{
  height:4vh;
  width:10vw;
}
.icon{
  box-shadow:0 0 25px black ;
  background: white;
  height: fit-content;
  width: fit-content;
  margin:10vh auto;
}
</style>
