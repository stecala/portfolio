<template>
  <header class="container-fluid">
    <div class="row position-relative">
      <!-- logo zone -->
      <div class="col-6 logo-container">
          <i class="fa-solid fa-ghost"></i>
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
        <div class="position-absolute hamburger-list" :class="isClicked===true ? 'd-block slide-in-elliptic-right-fwd' : isFirst() ">
            <ul>
              <li v-for="link in navbarItems" :key="link.id">
                <span class="number-navbar">0{{link.id}}.</span>
                <span>&nbsp;{{link.text}}</span>
              </li>
            </ul>
        </div>
        <!-- navbar lg -->
        <div class="d-none d-lg-block navbar-lg-container">
          <ul class="justify-content-end d-flex no-wrap">
            <li v-for="link in navbarItems" :key="link.id" class="pe-5">
                <span class="number-navbar">0{{link.id}}.</span>
                <span>&nbsp;{{link.text}}</span>
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
          url : '',
        },
        {
          id : 2,
          text : 'Experience',
          url : '',
        },
        {
          id : 3,
          text : 'Work',
          url : '',
        },
        {
          id : 4,
          text : 'Contact',
          url : '',
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

.logo-container{
  height: 80px;
}

.container-hamburger-icon{
  height: 80px;
  .hamburger-list{
    top: 80px;
    right: 0;
    width: 200px;
    
  }
}

.navbar-lg-container{
  padding-top: 20px;
  ul{
    list-style: none;
    padding: 0;
    height: 40px;
    font-family: 'Inconsolata', monospace;
    li{
      display: inline-block;
      cursor: pointer;
      font-weight: 700;
      .number-navbar{
        color: var(--note);
        font-weight: 400;
      }
      &:hover{
        color: var(--title-color);
        transition: all 0.5s ease-in;
      }
    }
  }
}



.slide-in-elliptic-right-fwd {
	-webkit-animation: slide-in-elliptic-right-fwd 0.9s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	animation: slide-in-elliptic-right-fwd 0.9s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}
@-webkit-keyframes slide-in-elliptic-right-fwd {
  0% {
    -webkit-transform: translateX(800px) rotateY(-30deg) scale(0);
            transform: translateX(800px) rotateY(-30deg) scale(0);
    -webkit-transform-origin: -100% 50%;
            transform-origin: -100% 50%;
    opacity: 0;
  }
  100% {
    -webkit-transform: translateX(0) rotateY(0) scale(1);
            transform: translateX(0) rotateY(0) scale(1);
    -webkit-transform-origin: -1800px 50%;
            transform-origin: -1800px 50%;
    opacity: 1;
  }
}
@keyframes slide-in-elliptic-right-fwd {
  0% {
    -webkit-transform: translateX(800px) rotateY(-30deg) scale(0);
            transform: translateX(800px) rotateY(-30deg) scale(0);
    -webkit-transform-origin: -100% 50%;
            transform-origin: -100% 50%;
    opacity: 0;
  }
  100% {
    -webkit-transform: translateX(0) rotateY(0) scale(1);
            transform: translateX(0) rotateY(0) scale(1);
    -webkit-transform-origin: -1800px 50%;
            transform-origin: -1800px 50%;
    opacity: 1;
  }
}

.slide-out-elliptic-right-bck {
	-webkit-animation: slide-out-elliptic-right-bck 0.7s ease-in both;
	animation: slide-out-elliptic-right-bck 0.7s ease-in both;
}
@-webkit-keyframes slide-out-elliptic-right-bck {
  0% {
    -webkit-transform: translateX(0) rotateY(0) scale(1);
            transform: translateX(0) rotateY(0) scale(1);
    -webkit-transform-origin: -1800px 50%;
            transform-origin: -1800px 50%;
    opacity: 1;
  }
  100% {
    -webkit-transform: translateX(1000px) rotateY(-30deg) scale(0);
            transform: translateX(1000px) rotateY(-30deg) scale(0);
    -webkit-transform-origin: -100% 50%;
            transform-origin: -100% 50%;
    opacity: 1;
  }
}
@keyframes slide-out-elliptic-right-bck {
  0% {
    -webkit-transform: translateX(0) rotateY(0) scale(1);
            transform: translateX(0) rotateY(0) scale(1);
    -webkit-transform-origin: -1800px 50%;
            transform-origin: -1800px 50%;
    opacity: 1;
  }
  100% {
    -webkit-transform: translateX(1000px) rotateY(-30deg) scale(0);
            transform: translateX(1000px) rotateY(-30deg) scale(0);
    -webkit-transform-origin: -100% 50%;
            transform-origin: -100% 50%;
    opacity: 1;
  }
}
</style>