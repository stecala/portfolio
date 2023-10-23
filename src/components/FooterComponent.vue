<template>
  <footer class="position-absolute" >
      <div class="row" v-scrollanimation>
        <div class="col-12 d-md-none">
          <ul class="smartphone-ul">
            <li v-for="social in socials" :key="social.id">
              <a :href="social.link" :target="(social.id < socials.length - 1) ? '_blank' : ''">
                <i :class="social.icon"></i>
              </a>
            </li>
          </ul>
        </div>
        <div class="d-none col-12 d-md-block d-lg-none">
          <ul class="tablet-ul ">
            <li v-for="social in socials" :key="social.id">
              <a :href="social.link" :target="(social.id < socials.length - 1) ? '_blank' : ''">
                <i :class="social.icon"></i>
              </a>
            </li>
          </ul>
        </div>
      </div>
  </footer>
</template>

<script>
export default {
  data: function(){
    return{
      socials : [
        {
          id: 0,
          icon : 'fa-brands fa-github',
          link : 'https://github.com/stecala',
        },
        {
          id: 1,
          icon : 'fa-brands fa-instagram',
          link : 'https://www.instagram.com/stefano.calarota/',
        },
        {
          id: 2,
          icon : 'fa-brands fa-linkedin-in',
          link : 'https://www.linkedin.com/in/stefano-calarota-64b623226/',
        },
        {
          id: 3,
          icon : 'fa-brands fa-codepen',
          link : 'https://codepen.io/stecala',
        },
        {
          id: 4,
          icon: 'fa-solid fa-angle-up',
          link:'#start',
        }
      ]
    
    }
  }
}
</script>

<style scoped lang="scss">
footer{
  right:5px;
  top: 35%;
}
  .smartphone-ul{
    list-style: none;
    text-align: end;
    li{
      font-size: 2rem;
      padding: 10px;
      a{
        color: var(--note);
      }
    }
  }
  .tablet-ul{
    list-style: none;
    text-align: end;
    li{
      display: inline-block;
      font-size: 2rem;
      padding: 10px;
      a{
        color: var(--note);
      }
    }
  }

.before-enter{
  opacity: 0;
}
.enter{
	-webkit-animation: tilt-in-right-1 2s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	animation: tilt-in-right-1 2s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}

@-webkit-keyframes tilt-in-right-1 {
  0% {
    -webkit-transform: rotateX(-30deg) translateX(300px) skewX(30deg);
            transform: rotateX(-30deg) translateX(300px) skewX(30deg);
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateX(0deg) translateX(0) skewX(0deg);
            transform: rotateX(0deg) translateX(0) skewX(0deg);
    opacity: 1;
  }
}
@keyframes tilt-in-right-1 {
  0% {
    -webkit-transform: rotateX(-30deg) translateX(300px) skewX(30deg);
            transform: rotateX(-30deg) translateX(300px) skewX(30deg);
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateX(0deg) translateX(0) skewX(0deg);
            transform: rotateX(0deg) translateX(0) skewX(0deg);
    opacity: 1;
  }
}
</style>