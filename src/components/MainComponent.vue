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

    <div class="container-lg puff-in-center container-snap">
      <div class="small-container"> 
        <section>
          <div class="info-container">
            <p class="divider mb-3">
              &#60; &#62;
            </p>
            <p class="small-text ps-3">Hi, name is </p>
            <p class="name ps-3">Stefano Calarota. </p>
            <p class="big-description ps-3">I'm an in-progress Web Developer.</p>

            <p class="text d-none d-lg-block">In my 30s I decided to change my life attending the Boolean Tech Academy course to learn how to became a Full Stack Web Developer.<br>
              My aim for the near future is to aplly what I studied in these months and <span>make it my job.</span>
            </p>
            <p class="text-mobile d-lg-none ps-3">In my 30s I decided to change my life attending the Boolean Tech Academy course to learn how to became a Full Stack Web Developer.<br>
              My aim for the near future is to aplly what I studied in these months and <span>make it my job.</span>
            </p>
            <p class="divider mt-5" >
              &#60;/&#62;
            </p>
          </div>
        </section>
        <section>
          <h3>Ciao</h3>
        </section>
        <section>
          <h3>come</h3>
        </section>
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
@import '../assets/style/slide-in-bottom.scss';
@import '../assets/style/puff-in.scss';
  main{
    
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
  .container-snap{
    width: 100vw;
    height: calc(100vh - 120px);

    .small-container{
      width: 100%;
      height: 100%;
      scroll-snap-type: y mandatory;
      overflow-y: scroll;
      scrollbar-width: none;

      &::-webkit-scrollbar {
        display: none;
      }
      
      section{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        width: 100%;
        scroll-snap-align: start;
      }
    }
  }
</style>
