<template>
<div class="cardCd" :class="array.length >= 5 ? 'widthAll' : 'widthstandard'" >
    <div class="imgbox"><img :src="cd.poster" alt="" @error="defaultimg"></div>
    <h2>{{cd.title}}</h2>
    <h3>{{cd.author}} <h3>{{cd.year}}</h3> </h3>
    
 </div>
</template>

<script>
    import imgLogo from '@/assets/img/logo.png'
export default {
    name:'CdCard',
props:{
    cd:Object,
    array:Array
},
methods:{
    defaultimg(e){
        e.target.src = imgLogo
    }
},

}
</script>

<style lang="scss" scoped>
    .widthAll{
        width: calc( 100% / 5 - 40px);
    }
    .widthstandard{
        width: 300px;
        height: 500px;
    }
        .cardCd{
            height: 430px;
            margin: 20px;
            padding: 15px;
            background-color: #2e3a46;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            .imgbox{
                width: 90%;
                height: 60%;
                img{
                width: 100%;
                height: 100%;
                object-fit: cover;
                object-position: top;
                }
            }
            h2{
                text-transform: uppercase;
                color: white;
            }
            h3{
                color: rgba(185, 185, 185, 0.5);
            }
          
        }

</style>