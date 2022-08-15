<template>
  <header class="container-fluid">
    <div class="row">
      <div class="col-6 bg-success">
          <i class="fa-solid fa-ghost"></i>
      </div>
      <div class="col-6 container-hamburger-icon position-relative">
        <input type="checkbox" id="hi">
          <label class="menu" for="hi">
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
          </label>
      </div>
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
@import '../assets/style/hamburger-icon.scss';
.container-hamburger-icon{
  height: 80px;
}
</style>