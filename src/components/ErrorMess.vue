<template>
  <div class="container">
    <h2>
        {{e.message}}
        <p>We apologize for the inconvenience...</p>
    </h2>
  </div>
</template>

<script>
export default {
name:'ErrorMess',
props:{
    e:String
}
}

</script>

<style lang="scss" scoped>
 .container{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        h2{
            color: red;
            p{
                color: white;
            }
        }
    }
</style>