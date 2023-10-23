<template>
    <div class="row">
        <!-- MOBILEPHONE -->
        <div class="col-12 mt-3 d-md-none">
            <ul class="header-skills-mobile">
                <li v-for="(skill, index) in skills" :key="index" @click="setCurrentSkill(skill)">
                    {{skill}}
                    <div class="marker" :class="skill == selectedSkill ? 'visible' : 'invisible'"></div>
                </li>
            </ul>
        </div>
        <div class="col-12 mt-2  d-md-none">

            <!-- Hard Skill mobile -->
            <ul v-if="selectedSkill=='Hard Skills'" class="skill-to-select-list">
                <li v-for="type in hardSkillList" :key="type.id" :class="selectedSkill == 'Hard Skills' && type.type === selectedHardSkill ? 'selected' : ''" @click="setCurrentHardSkill(type.type)" class="hover">
                    {{type.type}}
                </li>
            </ul>

            <!-- Soft Skill mobile -->
            <ul class="skill-to-select-list" v-if="selectedSkill=='Soft Skills'">
                <li v-for="type in softSkillList" :key='type.id' @click="setCurrentSoftSkill(type.name)" :class="{'selected' : selectedSoftSkill == type.name}">
                    {{type.name}}
                </li>
            </ul>

            <!-- Lenguages mobile -->
            <ul v-if="selectedSkill=='Languages'" class="skill-to-select-list" >
                <li v-for="lang in languagesList" :key="lang.id" :class="{'selected' : selectedLanguage == lang.lang}" @click="setCurrentLanguage(lang.lang)">
                    {{lang.lang}}
                </li>
            </ul>
        </div>

        <div class="col-12  d-md-none">
            
            <!-- Hardskill -->
            <ul v-if="selectedSkill=='Hard Skills'" class="lang">
                <li v-for="PCLang in hardSkillList[counterHS].langs" :key="PCLang.id" :class="(PCLang.id <= hardSkillList[counterHS].langs.length) ? 'border-b' : '' " class="ps-5"> 
                    <span class="icon-container"><i :class="PCLang.icon"></i></span>{{PCLang.name}}
                </li>
           </ul>
            
            <!-- SoftSkill -->
            <ul class="lang" v-if="selectedSkill=='Soft Skills'">
             <li v-for="skill in softSkillList[counterSS].description" :key="skill.id" :class="{
             'border-b-social' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Social', 
             'border-b-personal' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Personal',
             'border-b-methodical' : skill.id < softSkillList[counterSS].description.length && selectedSoftSkill == 'Methodical'
             }" class="ps-5">
                <span class="icon-container"><i :class="skill.icon"></i></span>{{skill.skill}}
             </li>
           </ul>           

           <!-- Lang -->
            <ul class="lang" v-if="selectedSkill=='Languages' ">
                <li v-for="lang in languagesList" :key="lang.id" v-show="lang.lang == selectedLanguage" class="px-0">
                    <div class="img-container"><img :src="lang.img" :alt="lang.lang"></div>
                    <div class="txt-container ps-4"> 
                        {{lang.description}}
                    </div> 
                </li>
            </ul>
        </div>






        <!-- MD OR MORE -->
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
             }" class="ps-5 d-flex align-items-start">
                <span class="icon-container"><i :class="skill.icon"></i></span>{{skill.skill}}
             </li>
           </ul>

           <!-- Languages -->
            <ul class="lang" v-if="selectedSkill == 'Languages'">
                <li v-for="lang in languagesList" :key="lang.id" class="border-b">
                   <div class="img-container"><img :src="lang.img" :alt="lang.lang"></div>
                    <div class="txt-container px-3"> 
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
            selectedLanguage : 'Italian',
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
        },
        setCurrentLanguage(clicked){
            this.selectedLanguage= clicked
        }
       
    }
}
</script>

<style scoped lang="scss">
@import '../assets/style/skill-to-md.scss';

.header-skills-mobile,
.skill-to-select-list{
    list-style: none;
    display: flex;
}
.header-skills-mobile{
    justify-content: space-around;
}
.skill-to-select-list{
    justify-content: space-around;
}    
.marker{
    width: 100%;
    height: 3px;
    border-radius: 1.5px;
    background-color: var(--title-color);
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
        .icon-container{
            padding-right: 20px;
            font-size: 1.5rem;
            color: var(--note);
        }
        .img-container{
            width: 50px;
            height: 50px;
            img{
            width: 100%;
            }
        }
        .txt-container{
            width: 80%;
            min-height: 60px;
        }
    }
    
}
 </style>