<template>
  <div class="col-12 mt-5 position-relative">
    <div class="row">
        <div class="col-7">
            <div class="img-container" v-for="work in worksList" :key="work.id" v-show="(currentIndex == work.id)">
                <img :src="work.img" :alt="work.name" v-scrollanimation>
            </div>
        </div>
        <div class="col-5 pt-5">
                <p class="project text-end"> 
                    Featured Project
                </p>
                <div v-for="work in worksList" :key="work.id"  v-show="(currentIndex == work.id)" class="container-vfor">
                    <p class="title">
                        {{work.name}}
                    </p>
                    <div class="py-4 description" v-scrollanimation>
                        {{work.description}}
                    </div>
                    <ul class="tech mt-3">
                        <li v-for="tech in work.technologyUsed" :key="tech" class="ps-3">
                            {{tech}}
                        </li>
                    </ul>
                    <div class="icon me-5">
                        <a :href="work.link" target="_blank">
                            <i class="fa-brands fa-github"></i>
                        </a>
                    </div>
                </div>
        </div>
    </div>
    <div class="next" @click="nextSlide(), changeStatusForAnimationR()" :class="{'jello' : setAnimationRight }">
        <i class="fa-solid fa-arrow-right"></i>
    </div>
    <div class="prev" @click="prevSlide(), changeStatusForAnimationL()" :class="{'jello' : setAnimationLeft }">
        <i class="fa-solid fa-arrow-left"></i>
    </div>
  </div>
</template>

<script>
export default {
    data : function(){
        return{
            worksList : [
                {
                    id : 0,
                    img : '/img/carousel/DC-Comics.png',
                    name : 'DC Comics clone',
                    description : 'A page that reproduces DC comics original website created using VueJs. Each section is composed of different components and populated by arrays of objects',
                    technologyUsed : ['VS Code', 'VueJs', 'CSS', 'Bootstrap'],
                    link : 'https://github.com/stecala/vue-dc-comics',

                },
                {
                    id : 1,
                    img : '/img/carousel/Netflix.png',
                    name : 'Netflix Search',
                    description : 'An application of Api\'s calls: the Homepage collects the most popular Films and TV series. It is also possible to search for a specific film title. Data are taken from TMDB.',
                    technologyUsed : ['VS Code', 'VueJs', 'Scss', 'Bootstrap', 'Axios'],
                    link : 'https://github.com/stecala/vue-boolflix',
                },
                {
                    id : 2,
                    img : '/img/carousel/Playstation.png',
                    name : 'Playstation clone',
                    description : 'Introduction to Front-end: a basic Web page that reproduces Playstation Home page using Bootstrap. 100% responsive for mobile phone.',
                    technologyUsed : ['VS Code', 'HTML5', 'CSS', 'Bootstrap'],
                    link : 'https://github.com/stecala/htmlcss-playstation',
                },
                {
                    id : 4,
                    img : '/img/carousel/whatsapp.png',
                    name : 'Whatsapp Web clone',
                    description : 'Example of a Web App developed using Vuejs. I recreated the Whatsapp Web App with a list of previous chats and the possibility to have a brief conversation with a CHAT-BOT! ',
                    technologyUsed : ['VS Code', 'Vuejs', 'CSS', 'Bootstrap'],
                    link : 'https://github.com/stecala/vue-boolzapp',
                },
                {
                    id : 3,
                    img : '/img/carousel/spotify.png',
                    name : 'Homepage Spotify',
                    description : 'Another Front-end project built with Bootstrap. I reproduced the Home page of Spotify Web App. Good news! it\'s completely responsive.  ',
                    technologyUsed : ['VS Code', 'HTML5', 'CSS', 'Bootstrap'],
                    link : 'https://github.com/stecala/html-css-spotifyweb',
                },
            ], 
            currentIndex : 0,
            setAnimationRight : false,
            setAnimationLeft : false,
        }
    },
    methods: {
        nextSlide(){
            this.currentIndex++
            if(this.currentIndex == this.worksList.length){
                this.currentIndex = 0
            }
        },
        prevSlide(){
            this.currentIndex--
            if(this.currentIndex < 0){
                this.currentIndex = this.worksList.length - 1
            }
        },
        changeStatusForAnimationR(){
            this.setAnimationRight = true
            setTimeout(()=>{
                this.setAnimationRight = false
            },500)
        },
        changeStatusForAnimationL(){
            this.setAnimationLeft = true
            setTimeout(()=>{
                this.setAnimationLeft = false
            },500)
        }
    }, 
}
</script>

<style lang="scss" scoped>
@import '../assets/style/jello.scss';
.col-12{
    max-height: 409px;
}
.img-container{
    width: 100%;
    height: 100%;
    img{
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }
}

.project{
    color:  var(--note);
}


.container-vfor{
    .title{
        font-size: 2rem;
        color: var(--title-color);
        font-weight: 700;
        text-align: end;
    }

    .tech{
        list-style: none;
        display: flex;
        justify-content: end;
        li{
            display: inline-block;
            font-size: 0.9;
        }
    }
    .description{
        font-size: 1.1;
        padding: 0 20px;
        border-radius: 10px;
        background-color: rgb(31, 31, 31);
        transition: 0.5s ease-in;
        &:hover{
            box-shadow: 5px 5px 5px rgba(51, 51, 51, 0.596);
        }
    }
    .icon{
        font-size: 2rem;
        text-align: end;
        a{
            text-decoration: none;
            color: var(--note);
        }
    }
}


.next,
.prev{
    position: absolute;
    bottom: -20px;
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: var(--title-color);
    color: black;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}
.next{
    right: 0;
}
.prev{
    left: 0;
}


.before-enter{
    opacity: 0;
}
.enter{
	-webkit-animation: swing-in-right-bck 0.8s cubic-bezier(0.175, 0.885, 0.320, 1.275) both;
    animation: swing-in-right-bck 0.8s cubic-bezier(0.175, 0.885, 0.320, 1.275) both;
}
@-webkit-keyframes swing-in-right-bck {
  0% {
    -webkit-transform: rotateY(70deg);
            transform: rotateY(70deg);
    -webkit-transform-origin: right;
            transform-origin: right;
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateY(0);
            transform: rotateY(0);
    -webkit-transform-origin: right;
            transform-origin: right;
    opacity: 1;
  }
}
@keyframes swing-in-right-bck {
  0% {
    -webkit-transform: rotateY(70deg);
            transform: rotateY(70deg);
    -webkit-transform-origin: right;
            transform-origin: right;
    opacity: 0;
  }
  100% {
    -webkit-transform: rotateY(0);
            transform: rotateY(0);
    -webkit-transform-origin: right;
            transform-origin: right;
    opacity: 1;
  }
}
</style>