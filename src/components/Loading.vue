<template>
  <div class="container">
    <h2>Loading files....</h2>
  </div>
</template>

<script>
export default {
name:'LoadingMess'
}
</script>

<style lang="scss" scoped>
    .container{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        h2{
            color: white;
        }
    }
</style>