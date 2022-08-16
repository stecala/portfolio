<template>
  <main>
    <div class="social-container position-fixed slide-in-bottom d-none d-lg-block">
      <ul>
        <li v-for="social in socialList" :key="social.id">
          <a :href="social.url" target="_blank">
            <i :class="social.icon"></i>
          </a>
        </li>
      </ul>
    </div>

    <div class="container-lg puff-in-center">
      <div class="info-container">
        <p class="divider mb-3">
          &#60; &#62;
        </p>
        <p class="small-text">Hi, name is </p>
        <p class="name">Stefano Calarota. </p>
        <p class="big-description">I'm an in-progress Web Developer.</p>

        <p class="text d-none d-lg-block">In my 30s I decided to change my life attending the Boolean Tech Academy course to learn how to became a Full Stack Web Developer.<br>
          My aim for the near future is to aplly what I studied in these months and <span>make it my job.</span>
        </p>
        <p class="text-mobile d-lg-none">In my 30s I decided to change my life attending the Boolean Tech Academy course to learn how to became a Full Stack Web Developer.<br>
          My aim for the near future is to aplly what I studied in these months and <span>make it my job.</span>
        </p>
        <p class="divider mt-5" >
          &#60;/&#62;
        </p>
      </div>
    </div>
  </main>
</template>

<script>

export default {
  props :{
  },
  data : function(){
    return{
      socialList : [
        {
          id : 0, 
          icon : 'fa-brands fa-github',
          url : 'https://github.com/stecala',
        },
        {
          id : 1,
          icon : 'fa-brands fa-instagram',
          url : 'https://www.instagram.com/stefano.calarota/',
        },
        {
          id : 2,
          icon : 'fa-brands fa-linkedin-in',
          url : 'https://www.linkedin.com/in/stefano-calarota-64b623226/',
        },
        {
          id : 3,
          icon : 'fa-brands fa-codepen',
          url : 'https://codepen.io/stecala',
        },
      ],

    }
  },
}
</script>

<style scoped lang="scss">
  main{
    margin-top: 80px;
    .social-container{
      bottom: 0;
      left: 5%;
      ul{
        list-style: none;
        padding: 0;
        li{
          a{
            font-size: 2rem;
            color: var(--note);
            transition: all 0.5s ;
            &:hover{
              color: var(--title-color); 
            }
          }
        }
      }
    }
    .info-container{
      max-width: 750px;
      margin: 100px auto;
      .small-text{
        color: var(--note);
        font-size: 1.5rem;
      }
      .name{
        color: var(--title-color);
        font-size: 2.7rem;
        font-weight: 700;
      }
      .big-description{
        color: var(--note);
        font-size: 2.7rem;
        font-weight: 700;
        line-height: 45px;
      }
      .text{
        width: 85%;
        span{
          color: var(--note);
        }
      }
      .text-mobile{
        width: 90%;
        span{
          color: var(--note);
        }
      }
      .divider{
        text-align: center;
        font-size: 2.5rem;
        font-weight: 600;
      }
    }
  }

.puff-in-center {
	-webkit-animation: puff-in-center 0.7s cubic-bezier(0.470, 0.000, 0.745, 0.715) both;
	animation: puff-in-center 0.7s cubic-bezier(0.470, 0.000, 0.745, 0.715) both;
  animation-delay: .7s;
}

@-webkit-keyframes puff-in-center {
  0% {
    -webkit-transform: scale(2);
            transform: scale(2);
    -webkit-filter: blur(4px);
            filter: blur(4px);
    opacity: 0;
  }
  100% {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-filter: blur(0px);
            filter: blur(0px);
    opacity: 1;
  }
}
@keyframes puff-in-center {
  0% {
    -webkit-transform: scale(2);
            transform: scale(2);
    -webkit-filter: blur(4px);
            filter: blur(4px);
    opacity: 0;
  }
  100% {
    -webkit-transform: scale(1);
            transform: scale(1);
    -webkit-filter: blur(0px);
            filter: blur(0px);
    opacity: 1;
  }
}



.slide-in-bottom {
	-webkit-animation: slide-in-bottom 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
	animation: slide-in-bottom 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
  animation-delay: 1s;
}
@-webkit-keyframes slide-in-bottom {
  0% {
    -webkit-transform: translateY(1000px);
            transform: translateY(1000px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
            transform: translateY(0);
    opacity: 1;
  }
}
@keyframes slide-in-bottom {
  0% {
    -webkit-transform: translateY(1000px);
            transform: translateY(1000px);
    opacity: 0;
  }
  100% {
    -webkit-transform: translateY(0);
            transform: translateY(0);
    opacity: 1;
  }
}
</style>
