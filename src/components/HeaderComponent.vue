<template>
  <div class="container">
    <div class="containerLogo"><img src="https://ajourneyintosound.de/wp-content/uploads/2019/02/spotify_logo.png" alt="spotify-logo-small"></div>
  </div>
</template>

<script>
export default {
    name: 'HeaderComponent',
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
</style>