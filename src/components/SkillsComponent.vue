<template>
    <div class="row">
        <div class="col-12 mt-4">
            <ul>
                <li v-for="skill in skills" :key="skill" @click="setCurrentSkill(skill)">
                    {{skill}}
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
            selectedSkill : 'Hard Skill',
        }
    },
    methods :{
        setCurrentSkill(clicked){
            this.selectedSkill = clicked
            console.log(this.selectedSkill)
        }
    }
}
</script>

<style scoped lang="scss">
    ul{
        list-style: none;
        width: 100%;
        display: flex;
        justify-content: space-around;
        padding: 0;
        li{
            display: inline-block;
            cursor: pointer;
            font-size: 1.5rem;
        }
    }
</style>