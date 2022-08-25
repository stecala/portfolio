<template>
    <div class="row">
        <div class="col-12 mt-5 d-none d-md-block">
            <ul class="header-skills">
                <li v-for="skill in skills" :key="skill" @click="setCurrentSkill(skill)">
                    {{skill}}
                    <div class="marker" :class="skill == selectedSkill ? 'visible' : 'invisible'"></div>
                </li>
            </ul>
        </div>

        <div class="col-3 position-relative d-none d-md-block">
            
            <!-- Hard skill -->
            <ul class="list-left" v-if="selectedSkill=='Hard Skills'">
                <li v-for="type in hardSkillList" :key="type.id" :class="selectedSkill == 'Hard Skills' && type.type === selectedHardSkill ? 'selected' : ''" @click="setCurrentHardSkill(type.type)" class="hover">
                    {{type.type}}
                </li>
            </ul>

            <!-- Soft skill -->
            <ul class="list-left" v-if="selectedSkill=='Soft Skills'">
                <li v-for="type in softSkillList" :key='type.id' @click="setCurrentSoftSkill(type.name)" :class="{'selected' : selectedSoftSkill == type.name}" class="hover">
                    {{type.name}}
                </li>
            </ul>
            
            <!-- Languages -->
            <ul v-if="selectedSkill=='Languages'" class="menu-lang" >
                <li v-for="lang in languagesList" :key="lang.id" class="hover" >
                    {{lang.lang}}
                </li>
            </ul>
            <div class="doodle-container-plane">
                <img src="/img/plane.svg" alt="doodle">
            </div>
            <div class="doodle-container-lamp d-md-none d-lg-block">
                <img src="/img/lamp.svg" alt="doodle lamp">
            </div>
        </div>
        <div class="col-9 d-none d-md-block">
            
            <!-- Hard skill -->
           <ul v-if="selectedSkill=='Hard Skills'" class="lang">
                <li v-for="PCLang in hardSkillList[counterHS].langs" :key="PCLang.id" :class="(PCLang.id <= hardSkillList[counterHS].langs.length) ? 'border-b' : '' " class="ps-5"> 
                    <span class="icon-container"><i :class="PCLang.icon"></i></span>{{PCLang.name}}
                </li>
           </ul>

            <!-- Soft skill -->
           <ul class="lang" v-if="selectedSkill=='Soft Skills'">
             <li v-for="skill in softSkillList[counterSS].description" :key="skill.id" :class="{
             'border-b-social' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Social', 
             'border-b-personal' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Personal',
             'border-b-methodical' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Methodical'
             }" class="ps-5">
                <span class="icon-container"><i :class="skill.icon"></i></span>{{skill.skill}}
             </li>
           </ul>

           <!-- Languages -->
            <ul class="lang" v-if="selectedSkill == 'Languages'">
                <li v-for="lang in languagesList" :key="lang.id" class="border-b">
                   <div class="img-container"><img :src="lang.img" :alt="lang.lang"></div>
                    <div class="txt-container"> 
                        {{lang.description}}
                    </div> 
                </li>
            </ul>

        </div>
    </div>
</template>

<script>
export default {
    data : function(){
        return{
            skills : ['Hard Skills' , 'Soft Skills' , 'Languages'],
            selectedSkill : 'Hard Skills',
            selectedHardSkill : 'Frontend',
            selectedSoftSkill : 'Social',
            counterHS : 0,
            counterSS : 0,
            hardSkillList: [
                {
                    id : 0, 
                    type : 'Frontend',
                    langs : [
                        {
                            id : 1,
                            icon : 'fa-brands fa-html5', 
                            name : 'HTML',
                        },
                        {
                            id: 2,
                            icon : 'fa-brands fa-css3', 
                            name : 'CSS',
                            description : '',
                        },
                        {
                            id: 3,
                            icon : 'fa-brands fa-bootstrap', 
                            name : 'Bootstrap',
                            description: '',
                        },
                        {
                            id: 4,
                            icon : 'fa-brands fa-sass', 
                            name : 'Sass',
                            description : '',
                        },
                        {
                            id: 5,
                            icon : 'fa-brands fa-square-js', 
                            name : 'Javascript',
                            description : '',
                        },
                        {
                            id: 6,
                            icon : 'fa-brands fa-vuejs', 
                            name : 'Vue.js',
                            description : '',
                        },
                    ],
                },
                {
                    id : 1, 
                    type : 'Backend',
                    langs : [
                        {
                            id: 1,
                            icon : 'fa-solid fa-compact-disc', 
                            name: 'MySQL',
                            description: '',
                        },
                        {
                            id: 2,
                            icon : 'fa-brands fa-php', 
                            name: 'PHP',
                            description: '',
                        },
                        {
                            id: 3,
                            icon : 'fa-brands fa-laravel', 
                            name: 'Laravel',
                            description: '',
                        },
                    ]
                },
            ],
            softSkillList: [
                {
                    id : 0,
                    name : 'Social',
                    description : [
                        {
                            id : 0,
                            icon : 'fa-solid fa-handshake', 
                            skill : 'TeamWork',
                        },
                        {
                            id : 1,
                            icon : 'fa-solid fa-bullhorn', 
                            skill : 'Comunication',
                        },
                        {
                            id : 2,
                            icon : 'fa-solid fa-user-tie', 
                            skill : 'Leadership',
                        },
                        {
                            id : 3,
                            icon : 'fa-solid fa-hand-holding-heart', 
                            skill : 'Emphaty',
                        },
                    ]
                },
                {
                    id : 1,
                    name : 'Personal',
                    description : [
                        {
                            id : 0,
                            icon : 'fa-solid fa-bullseye',
                            skill : 'Motivation',
                        },
                        {
                            id : 1,
                            icon : 'fa-solid fa-lightbulb',
                            skill : 'Creative Thinking',
                        },
                        {
                            id : 2,
                            icon : 'fa-solid fa-stopwatch',
                            skill : 'Time Management',
                        },
                        {
                            id : 3,
                            icon : 'fa-solid fa-arrow-up-right-dots',
                            skill : 'Willingness to Improve',
                        },
                    ],
                },
                {
                    id : 2,
                    name : 'Methodical',
                    description : [
                        {
                            id : 0,
                            icon: 'fa-solid fa-person-chalkboard',
                            skill: 'Presentation', 
                        },
                        {
                            id : 1,
                            icon: 'fa-solid fa-calculator',
                            skill: 'Analytical Skills', 
                        },
                        {
                            id : 2,
                            icon: 'fa-solid fa-microchip',
                            skill: 'Dealing with new Technology', 
                        },
                    ],
                },
            ],
            languagesList : [
                {
                    id : 0,
                    lang : 'Italian',
                    img : '/img/flags/italy.svg',
                    description : 'Native',
                },
                {
                    id : 1,
                    lang : 'English',
                    img : '/img/flags/england.svg',
                    description : 'Advanced level (B2) acquired during the schools and improved trought a 6-months staying in Spain',
                },
                {
                    id : 2,
                    lang : 'Spanish',
                    img : '/img/flags/spain.svg',
                    description : 'Advanced level in listening and reading (B2) acquired during the first years of highschool and refreshed living for 6 months in Girona',
                },
            ]
        }
    },
    methods :{
        setCurrentSkill(clicked){
            this.selectedSkill = clicked
            console.log(this.selectedSkill)
        },
        setCurrentHardSkill(clicked){
            this.selectedHardSkill = clicked
            if(clicked == 'Backend'){
                this.counterHS = 1
            }
            else{
                this.counterHS = 0
            }
            
        },
        setCurrentSoftSkill(clicked){
            this.selectedSoftSkill = clicked
            if(this.selectedSoftSkill == 'Social'){
                this.counterSS = 0
            }
            else if(this.selectedSoftSkill == 'Personal'){
                this.counterSS = 1
            }
            else{
                this.counterSS = 2
            }
            console.log(this.counterSS)
        }
       
    }
}
</script>

<style scoped lang="scss">
    .header-skills{
        list-style: none;
        width: 100%;
        display: flex;
        justify-content: space-around;
        padding: 0;
        li{
            display: inline-block;
            cursor: pointer;
            font-size: 1.5rem;
            border-radius: 5px;
            padding: 0 5px;
            &:hover{
                background-color: rgba(255, 255, 255, 0.199);
            }
            .marker{
                width: 100%;
                height: 3px;
                border-radius: 1.5px;
                background-color: var(--title-color);
            }
        }
    }
    .list-left{
        list-style: none;
        padding: 15px 0;
        li{
            margin-top: 25px;
            padding: 15px 10px;
            font-size: 1.3rem;
            cursor: pointer;
            border-radius: 10px ;
        }
        .hover:hover{
            background-color: rgba(245, 245, 220, 0.219);
        }
    }
    .selected{
        color: var(--title-color);
    }
    .lang{
        list-style: none;
        margin-top: 25px;
        margin-bottom: 0;
        padding: 0 10px;
        border-radius: 5px;
        min-height: 401px;

        li{
            padding: 15px;
            font-size: 1.2rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            .icon-container{
                padding-right: 20px;
                font-size: 1.5rem;
                color: var(--note);
            }
            .img-container{
                display: inline-block;
                width: 50px;
                height: 50px;
                img{
                width: 100%;
                }
            }
            .txt-container{
                display: inline-block;
                width: 80%;
                min-height: 60px;
                padding: 0 20px;
            }
        }
        
    }
    .doodle-container-plane{
        width: 100px;
        height: 100px;
        left: 0;
        bottom: -2%;
    }
    .doodle-container-lamp{
        width: 150px;
        height: 150px;
        top: -60%;
        left: 170%;
        transform: rotate(15deg);
    }
    .doodle-container-plane,
    .doodle-container-lamp
    {
        position: absolute;
        
        img{
            width: 100%;
        }
    }
    
    .col-3{
        padding-right: 0;
    }
    .col-9{
        padding-left: 0;
    }
    .border-b{
        border-bottom: 1px solid var(--note);
    }
   
    .border-b-social{
        border-bottom: 1px solid teal;
    }
    .border-b-personal{
        border-bottom: 1px solid #b10451;
    }
    .border-b-methodical{
        border-bottom: 1px solid rgb(202, 54, 13);
    }
    .menu-lang{
        list-style: none;
        padding: 25px 0;
        li{
            padding: 15px 10px;
            font-size: 1.3rem;
            border-radius: 10px 0 0 10px;
            &:nth-of-type(1){
                margin-top: 20px
            }
            &:nth-of-type(2){
                margin-top: 40px;
            }
            &:nth-of-type(3){
                margin-top: 55px;
            }
        }
    }
 </style>