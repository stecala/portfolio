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
        <section class="px-3 mt-5 ">
          <div class="row align-items-center">
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
@import '../assets/style/slide-in-left.scss';
@import '../assets/style/doodle-style.scss';
  main{
    
    .social-container{
      bottom: 0;
      left: 1.5%;
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
      margin: 0px auto;
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
        height: 108vh;
        width: 100%;
        scroll-snap-align: start;
        
        &:nth-of-type(2){
          justify-content: start;
          .text-section{
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
            
          }
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
        }
      }
    }
  }
</style>
