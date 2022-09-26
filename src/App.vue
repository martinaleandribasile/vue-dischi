<template>
  <div id="app">
    <LoadingMess v-if="loading"/>
    <ErrorMess v-if="error" :e='errorstring'/>
    <HeaderComponent/>
    <CdMain :CdArray=CdArray />
  </div>
</template>

<script>
import axios from 'axios'
import HeaderComponent from './components/HeaderComponent.vue';
import CdMain from './components/CdMain.vue';
import LoadingMess from '@/components/Loading.vue'
import ErrorMess from '@/components/ErrorMess.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    CdMain,
    LoadingMess,
    ErrorMess
  },
  data(){
    return{
      CdArray:[],
      loading:true,
      error:false,
      errorstring:''
    } 
  },
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data, status})=>{
        if(status===200){
          this.CdArray=data.response
          this.loading=false
        }
    })
    .catch(e=>{
      this.loading=false
      this.error=true
      this.errorstring=e
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
