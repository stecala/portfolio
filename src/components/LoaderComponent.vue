<template>
  <div class="container-logo slide-out-bck-tl" v-if="bootAnimation">
      <div class="img-container d-flex align-items-center">
        <img src="/img/SC_logo_white.svg" alt="image logo" class="animation-logo">
        <div class="line-1"></div>
        <div class="line-2"></div>
        <div class="line-3"></div>
        <div class="line-4"></div>
      </div>   
    </div>
</template>

<script>
export default {
    props:{
        bootAnimation: Boolean,
    }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/animation-loader.scss';

</style>