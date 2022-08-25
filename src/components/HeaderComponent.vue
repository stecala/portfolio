<template>
  <header class="container-fluid">
    <div class="row position-relative">
      <!-- logo zone -->
      <div class="col-6 logo-container slide-in-bck-top">
          <img src="/img/SC_logo_white.svg" alt="logo image" class="ps-3 pt-3">
      </div>

      <!-- navbar zone -->
      <div class="col-6 container-hamburger-icon position-relative">
        <!-- navbar mobile -->
        <div class="d-lg-none" >
          <input type="checkbox" id="hi" @click="changeStatus()">
            <label class="menu" for="hi">
              <div class="bar"></div>
              <div class="bar"></div>
              <div class="bar"></div>
            </label>
        </div>
        <div class="position-absolute hamburger-list py-3" :class="isClicked===true ? 'd-block slide-in-elliptic-right-fwd' : isFirst() ">
            <ul>
              <li v-for="link in navbarItems" :key="link.id" class="pe-3">
                <a :href="link.url">
                  <span class="number-navbar">0{{link.id}}.</span>
                  <span>{{link.text}}</span>
                </a>
              </li>
            </ul>
        </div>
        <!-- navbar lg -->
        <div class="d-none d-lg-block navbar-lg-container ">
          <ul class="justify-content-end d-flex no-wrap ">
            <li v-for="link in navbarItems" :key="link.id" class="pe-5 slide-in-top">
              <a :href="link.url">
                <span class="number-navbar">0{{link.id}}.</span>
                <span>&nbsp;{{link.text}}</span>
              </a>
            </li>
          </ul>
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
      counterForAnimation : 0,
      navbarItems : [
        {
          id : 1,
          text : 'About',
          url : '#about',
        },
        {
          id : 2,
          text : 'Skills',
          url : '#skill',
        },
        {
          id : 3,
          text : 'Works',
          url : '#works',
        },
        {
          id : 4,
          text : 'Contact',
          url : '#contact',
        },
      ]
    }
  },
  methods : {
    changeStatus(){
      this.counterForAnimation++
      this.isClicked = !this.isClicked
      console.warn(this.isClicked)
    },
    isFirst(){
      if(this.counterForAnimation == 0){
          return 'd-none'
      }
      else{
          return 'slide-out-elliptic-right-bck'
      }
    },
    
  }
}
</script>

<style scoped lang="scss">
@import '../assets/style/hamburger-icon.scss';
@import '../assets/style/animation-hamburger-list.scss';

a{
  color: var(--light);
  text-decoration: none;
  &:hover{
        color: var(--title-color);
        transition: all 0.5s ease-in;
      }
}
.logo-container{
  height: 80px;
  img{
    height: 100%;
  }
}

.container-hamburger-icon{
  height: 80px;
  .hamburger-list{
    top: 80px;
    right: 1px;
    width: 100vw;
    z-index: 1;
    background-color: var(--bg-dark);
    border-bottom: 2px solid var(--note);
    ul{
      list-style: none;
      padding: 0;
      text-align: center;
      font-weight: 700;
      li{
        padding-top: 20px;
        font-family: 'Inconsolata', monospace;
        display: inline-block;
      }
    }
  }
}

.number-navbar{
  color: var(--note);
  font-weight: 400;
}

.navbar-lg-container{
  padding-top: 30px;
  ul{
    list-style: none;
    padding-left: 16px;
    height: 40px;
    font-family: 'Inconsolata', monospace;
    li{
      display: inline-block;
      cursor: pointer;
      font-weight: 700;
      
      
    }
  }
}


.slide-in-top {
	-webkit-animation: slide-in-top 0.9s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	animation: slide-in-top 0.9s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}
@-webkit-keyframes slide-in-top {
  0% {
    -webkit-transform: translateY(-1000px);
            transform: translateY(-1000px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
            transform: translateY(0);
    opacity: 1;
  }
}
@keyframes slide-in-top {
  0% {
    -webkit-transform: translateY(-1000px);
            transform: translateY(-1000px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
            transform: translateY(0);
    opacity: 1;
  }
}

.slide-in-bck-top {
	-webkit-animation: slide-in-bck-top 0.6s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	animation: slide-in-bck-top 0.6s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}
@-webkit-keyframes slide-in-bck-top {
  0% {
    -webkit-transform: translateZ(700px) translateY(-300px);
            transform: translateZ(700px) translateY(-300px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateZ(0) translateY(0);
            transform: translateZ(0) translateY(0);
    opacity: 1;
  }
}
@keyframes slide-in-bck-top {
  0% {
    -webkit-transform: translateZ(700px) translateY(-300px);
            transform: translateZ(700px) translateY(-300px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateZ(0) translateY(0);
            transform: translateZ(0) translateY(0);
    opacity: 1;
  }
}
</style>