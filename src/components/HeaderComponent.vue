<template>
 <div class="header"> 
    <div class="container">
      <div class="containerLogo"><img src="https://ajourneyintosound.de/wp-content/uploads/2019/02/spotify_logo.png" alt="spotify-logo-small"></div>
    </div>
    <div class="container-sel">
      <div class="selection-container">
          <h3>Filtra per genere</h3>
          <select name="GenereCd"  @change="changeGender($event)">
              <option value="All">All</option>
              <option value="Jazz">Jazz</option>
              <option value="Metal">Metal</option>
              <option value="Pop">Pop</option>
              <option value="Rock">Rock</option>
          </select>
      </div>
      <div class="selection-container">
          <h3>Filtra per genere</h3>
          <select name="AuthorCd" @change="changeAuthor($event)">
              <option value="All">All</option>
              <option :value="item" v-for="item in author" :key="item" >{{item}}</option>
          </select>
      </div>
  </div>
  </div>
</template>

<script>
export default {
    name: 'HeaderComponent',
    data(){
        return{
            valuegender:'',
            valueauthor:''
        }
    },
   props:{
    author:Array
   },
    methods:{
    changeGender(event){
        this.valuegender = event.target.value
        this.$emit('generSel' , this.valuegender)
    },
    changeAuthor(event){
        this.valueauthor = event.target.value
        this.$emit('authorSel' , this.valueauthor)
    }
},
}
</script>

<style lang="scss" scoped>
.container{
    background-color: #2e3a46;
    padding: 10px;
    height: 10%;
    display: flex;
    align-items: center;
    .containerLogo{
    width: 100px;
    height: 100px;
    img{
        height: 100%;
    }
}
}
.container-sel{
        height: 10%!important;
        padding-right: 100px;
        padding-top: 20px;
        padding-bottom: 20px;
        background-color: #2e3a46;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-end;
        column-gap: 20px;
        .selection-container{
            display: flex;
            flex-direction: row;
            align-items: center;
            h3{
            color: white;
            padding-right: 10px;
            }
            select{
                padding: 5px;
                width: 100px;
            }
        }
      
    }
</style>