<template>
  <div id="app">
    <HeaderComponent @generSel="setSelectValue" @authorSel='setSelectAuthorVal' :author=authorsArray />
    <CdMain :CdArray=filteredCd />
    <LoadingMess v-if="loading"/>
    <ErrorMess v-if="error" :e='errorstring'/>
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
    ErrorMess,
    
  },
  data(){
    return{
      CdArray:[],
      loading:true,
      error:false,
      errorstring:'',
      chooseGener:'All',
      chooseAuthor:'All'
    } 
  },
  methods:{
    setSelectValue(value){
      this.chooseGener=value
    },
    setSelectAuthorVal(value){
      this.chooseAuthor=value
    }
  },
  computed:{
    filteredCd(){
      let cdFiltered=[]
      this.CdArray.forEach((element)=>{
        if(this.chooseAuthor!=="All"){
        this.chooseGener="All"
        }
        if(this.chooseGener!=="All"){
          this.chooseAuthor="All"
        }
        if(element.genre===this.chooseGener){
          cdFiltered.push(element)
        }
        else if(this.chooseAuthor===element.author){
          cdFiltered.push(element)
        }else if(this.chooseAuthor==='All' & this.chooseGener==='All'){
          cdFiltered=this.CdArray
        }
      })
      return cdFiltered
    },
    authorsArray(){
      let authorarray=[]
      this.CdArray.forEach(item =>{
        if(!authorarray.includes(item.author)){
          authorarray.push(item.author)
        }
      })
      return authorarray
    }
  },
  created(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then(({data, status})=>{
        if(status===200){
          this.CdArray=data.response
          this.loading=false
        }console.log(data.response)
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
