<template>
  <div id="app">
    <HeaderComponent />
    <MainComponent />
    <FooterComponent />
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
export default {
  components: {
    HeaderComponent,
    MainComponent, 
    FooterComponent,
  }
}
</script>

<style lang="scss">
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.2/css/all.min.css);
@import "~bootstrap/scss/bootstrap";
//font-family: 'Inconsolata', monospace; used for navbar
@import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@200;300;400;500;600&display=swap');
:root{
  --title-color : #FA4753;
  --bg-dark : #17181C;
  --light : #FFFFFF;
  --note : #9BA5C9;
}
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app{
  background-color: var(--bg-dark);
  color: var(--light);
}
</style>
