<template>
 <div class="header"> 
    <div class="container">
      <div class="containerLogo"><img src="https://ajourneyintosound.de/wp-content/uploads/2019/02/spotify_logo.png" alt="spotify-logo-small"></div>
    </div>
    <div class="container-sel">
    <div class="selection-container">
        <h3>Filtra per genere</h3>
        <select name="GenereCd"  @change="onChange($event)">
            <option value="All">All</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
        </select>
    </div>
    <div class="selection-container">
        <h3>Filtra per genere</h3>
        <select name="AuthorCd" id="">
            <option value="All">All</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Sting">Sting</option>
            <option value="Queen">Queen</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton Maiden</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jackson</option>
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
            value:''
        }
    },
    methods:{
    onChange(event){
        console.log(event)
        console.log('evento' ,event.target.value)
        this.value = event.target.value
        console.log('value' ,this.value)
        this.$emit('adminsel' , this.value)
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
        background-color: #1e2d3b;
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