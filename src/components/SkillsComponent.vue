<template>
    <div class="row">
        <div class="col-12 mt-4">
            <ul class="header-skills">
                <li v-for="skill in skills" :key="skill" @click="setCurrentSkill(skill)">
                    {{skill}}
                    <div class="marker" :class="skill == selectedSkill ? 'visible' : 'invisible'"></div>
                </li>
            </ul>
        </div>
        <!-- lg -->
        <div class="col-3">
            <ul class="list-left" v-if="selectedSkill=='Hard Skills'">
                <li v-for="type in hardSkillList" :key="type.id" :class="selectedSkill == 'Hard Skills' && type.type === selectedHardSkill ? 'selected' : ''" @click="setCurrentHardSkill(type.type)">
                    {{type.type}}
                </li>
            </ul>
            <ul class="list-left" v-if="selectedSkill=='Soft Skills'">
                <li v-for="type in softSkillList" :key='type.id' @click="setCurrentSoftSkill(type.name)" :class="{'social' : type.id == 0 , 'personal' : type.id == 1 , 'methodical' : type.id == 2 }">
                    {{type.name}}
                </li>
            </ul>
        </div>
        <div class="col-9">
           <ul v-if="selectedSkill=='Hard Skills'" class="lang selected">
                <li v-for="PCLang in hardSkillList[counterHS].langs" :key="PCLang.id" :class="(PCLang.id < hardSkillList[counterHS].langs.length) ? 'border-b' : '' "> 
                    <span class="icon-container"><i :class="PCLang.icon"></i></span>{{PCLang.name}}
                </li>
           </ul>
           <ul class="lang" v-if="selectedSkill=='Soft Skills'" :class="{'social' : counterSS == 0, 'personal' : counterSS == 1, 'methodical' : counterSS == 2}">
             <li v-for="skill in softSkillList[counterSS].description" :key="skill.id" :class="{
             'border-b-social' : skill.id < softSkillList[counterSS].description.length - 1 && selectedSoftSkill == 'Social', 
             'border-b-personal' : skill.id < softSkillList[counterSS].description.length - 1 && selectedSoftSkill == 'Personal',
             'border-b-methodical' : skill.id < softSkillList[counterSS].description.length - 1 && selectedSoftSkill == 'Methodical'
             }">
                <span class="icon-container"><i :class="skill.icon"></i></span>{{skill.skill}}
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
                            description : '',
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
            display: flex;
            justify-content: center;
            margin-top: 25px;
            padding: 15px 10px;
            font-size: 1.3rem;
            cursor: pointer;
            border-radius: 10px 0 0 10px;
        }
    }
    .lang{
        list-style: none;
        margin-top: 25px;
        margin-bottom: 0;
        padding: 0 10px;
        border-radius: 5px;
        height: 401px;
        li{
            padding: 15px;
            font-size: 1.2rem;
            font-weight: 600;
            .icon-container{
                padding-right: 20px;
                font-size: 1.5rem;
                color: var(--note);
            }
        }
    }
    .selected{
        background-color: #9ba5c975;
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
    .social{
        background-color:  rgba(0, 128, 128, 0.397);
    }
    .personal{
        background-color: #80003A;
    }
    .methodical{
        background-color: rgba(156, 39, 6);
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
 </style>