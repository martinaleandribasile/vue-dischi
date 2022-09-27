<template>
    <div class="container-list">
        <div class="CdList" >
            <CdCard :array="CdArray" v-for="cd in CdArray" :key="cd.title" :cd='cd'/>
        </div>
    </div>
</template>

<script>
    import CdCard from '@/components/CardCd.vue'
export default {
    name:'CdMain',
    props:{
        CdArray:Array,
    },
    components:{
        CdCard,
    }

}
</script>

<style lang="scss" scoped>
    .nowidth{
        width: auto;
    }
    .container-list{
        height: calc(100% - 188px);
        background-color: #1e2d3b;
        display: flex;
        align-items: center;
        .CdList{
            display: flex;
            flex-wrap: wrap;
            max-width: 1800px;
            margin: 0 auto;
        }
    }
</style>