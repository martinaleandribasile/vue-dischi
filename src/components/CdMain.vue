<template>
  <div class="container">
    <div class="CdList" >
        <CdCard v-for="cd in CdArray" :key="cd.title" :cd='cd'/>
    </div>
  </div>
</template>

<script>
    import CdCard from '@/components/CardCd.vue'
export default {
    name:'CdMain',
    data(){
        return{
            
        }
    },
    props:{
        CdArray:Array,
    },
    components:{
        CdCard
    }

}
</script>

<style lang="scss" scoped>
.container{
    height: calc(100% - 10%);
    background-color: #1e2d3b;
    display: flex;
    align-items: center;
    .CdList{
        display: flex;
        flex-wrap: wrap;
        width: 85%;
        margin: 0 auto;
    }
}
</style>