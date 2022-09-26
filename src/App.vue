<template>
  <div id="app">
   <HeaderComponent/>
   <CdMain :CdArray=CdArray />
  </div>
</template>

<script>
import axios from 'axios'
import HeaderComponent from './components/HeaderComponent.vue';
import CdMain from './components/CdMain.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    CdMain
  },
  data(){
    return{
      CdArray:[]
    } 
  },
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data})=>{
        console.log(data.response)
        this.CdArray=data.response
    })
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
#app {
  font-family: Helvetica, Arial, sans-serif;
  text-align: center;
  height: 100vh;
 
}
</style>
