<template>
  <header class="container-fluid">
    <div class="row">
      <div class="col-6 bg-success">
          <i class="fa-solid fa-ghost"></i>
      </div>
      <div class="col-6 container-hamburger-icon position-relative">
        <div class="d-lg-none" >
          <input type="checkbox" id="hi" @click="changeStatus()">
            <label class="menu" for="hi">
              <div class="bar"></div>
              <div class="bar"></div>
              <div class="bar"></div>
            </label>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data : function(){
    return{
      isClicked : false,
    }
  },
  methods : {
    changeStatus(){
      this.isClicked = !this.isClicked
      console.warn(this.isClicked)
    }
  }
}
</script>

<style scoped lang="scss">
@import '../assets/style/hamburger-icon.scss';
.container-hamburger-icon{
  height: 80px;
}
</style>