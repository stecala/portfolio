<template>
  <div id="app">
    <LoaderComponent :bootAnimation="bootAnimation" />
    <HeaderComponent v-if="bootAnimation === false" />
    <MainComponent v-if="bootAnimation === false" />
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import LoaderComponent from './components/LoaderComponent.vue'
export default {
  components: {
    HeaderComponent,
    MainComponent, 
    LoaderComponent,
  },
  data : function(){
    return{
      bootAnimation : true,
    }
  },
  methods : {
    removeLogo(){
      setTimeout(()=>{
        this.bootAnimation = false;
      },5000)
    }
  },
  created() {
    this.removeLogo()
  }
}
</script>

<style lang="scss">
@import url(https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@7.2.0/css/all.min.css);
@import "~bootstrap/scss/bootstrap";
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
  user-select: none;
  -webkit-user-select: none;
}
a {
  user-select: text;
  -webkit-user-select: text;
}

#app{
  background-color: var(--bg-dark);
  color: var(--light);
  min-height: 100vh;
  scrollbar-width: none;
  overflow: hidden;
}
</style>
