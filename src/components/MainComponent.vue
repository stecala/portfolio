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

    <div class="container-lg container-snap">
      <div class="small-container"> 
        <section class=" puff-in-center">
          <div class="info-container">
            <p class="divider mb-3">
              &#60; &#62;
            </p>
            <p class="small-text ps-3">Hi, name is </p>
            <p class="name ps-3">Stefano Calarota. </p>
            <p class="big-description ps-3">I'm an in-progress Web Developer.</p>

            <p class="text d-none d-lg-block ps-3">In my 30s I decided to change my life attending the Boolean Tech Academy course to learn how to became a Full Stack Web Developer.<br>
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
        <section class="px-3 mt-5" id="about" >
          <div class="row align-items-center " v-scrollanimation>
            <div class="col-12 col-lg-6 ">
              <div class="text-section row position-relative">
                <div class="col-12">
                  <span class="number-section">01.</span><span class="title-section"> About Me</span>
                </div>
                <div class="col-12 col-lg-12 mt-3">
                  <p>
                    Before my 30s I have held serveral job roles, I entered the world of work just after the high school exploring different paths without having a proper aspiration.<br>
                    My last and longer-lasting employment was as a <span class="note">CNC operator</span>: At that time I was in a small factory and my role was to create <span class="note">mechanical designs</span> for motorhome accessories.
                  </p>
                  <p>
                    I've always been interested in technology and informatic but I also pursued a passion for photography and post-production techniques using <span class="note">Adobe PhotoShop and Lightroom</span>. From this experiences I think I can say I'm good at self-taught!   
                  </p>
                  <p>
                    Six months ago I decided to take a different way to make my interests and my work converge attending an intense course to become a <span class="note">Full Stack Web Developer!</span> 
                  </p>
                </div>
            
                <div class="doodle-star position-absolute d-none d-xxl-block">
                  <img src="/img/star.svg" alt="doodle star">
                </div>
                <div class="doodle-rocket position-absolute d-none d-xxl-block">
                  <img src="/img/rocket.svg" alt="doodle rocket">
                </div>
              </div>

            </div>

            <div class="col-12 col-lg-6 mt-5">
              <div class="img-container position-relative">
                <img src="/img/foto profilo.jpg" alt="profile picture" class="">
                <div class="arrow-container-1 position-absolute d-none d-lg-block"></div>
                <div class="arrow-container-1-small position-absolute d-lg-none"></div>
                <div class="arrow-container-2 position-absolute d-none d-lg-block"></div>
                <div class="arrow-container-2-small position-absolute d-lg-none"></div>
                <div class="arrow-container-3 d-none d-xl-block position-absolute"></div>
                <div class="arrow-container-3-small d-lg-none position-absolute"></div>
              </div>
            </div>
          </div>
        </section>
        <section class="px-3 mt-5" id="skill">
          <div class="row align-items-center width-fix" v-scrollanimation>
            <div class="col-12">
              <span class="number-section">02.</span><span class="title-section"> Skills</span>
            </div>
            <SkillsComponent />
          </div>
        </section>
        <section class="px-3 mt-5" id="works">
          <div class="row align-items-center" v-scrollanimation>
            <div class="col-12">
              <span class="number-section">03.</span><span class="title-section"> Works</span>
            </div>
            <WorksComponent />
          </div>
        </section>
      </div>
    </div>
  </main>
</template>

<script>
import SkillsComponent from './SkillsComponent.vue';
import WorksComponent from './WorksComponents.vue';
export default {
  props :{
  },
  components :{
    SkillsComponent,
    WorksComponent,
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
@import '../assets/style/doodle-style.scss';
@import '../assets/style/info-container.scss';
@import '../assets/style/social-container.scss';   
    
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
        height: 108vh;
        width: 100%;
        scroll-snap-align: start;
        
        &:nth-of-type(2){
          justify-content: start;
          .img-container{
            text-align: center;
            margin: 0 auto;
            width: 50vw;
            max-width: 400px;
            height: 50vw;
            max-height: 400px;
            img{
              width: 100%;
              height: 100%;
              border-radius: 50%;
              object-fit: cover;
              position: relative;
            } 
          }
        &:nth-of-type(3){
          display: flex;
        }
    }
  }

  .enter{
    -webkit-animation: puff-in-center 0.7s cubic-bezier(0.470, 0.000, 0.745, 0.715) both;
    animation: puff-in-center 0.7s cubic-bezier(0.470, 0.000, 0.745, 0.715) both;
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
  }
  .before-enter{
    opacity: 0;
  }
  .number-section{
    color: var(--note);
    font-family: 'Inconsolata';
    font-size: 2rem;
  }
  .title-section{
    font-size: 2rem;
    font-weight: 700;
    color: var(--title-color);
  }
  .note{
    color: var(--note);
  }
  .width-fix{
    max-width: 821px;
  } 
}
</style>
