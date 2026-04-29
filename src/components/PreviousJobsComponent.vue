<template>
    <div class="col-12 mt-5 position-relative">
        <div class="row">
            
            <div class="col-3 position-relative d-md-block">
                <ul class="list-left" v-if="jobs.length > 0">
                    <li v-for="(job, index) in jobs" :key="index" class="hover me-3" @click="setCurrentJob(job)" :class="job === selectedJob ? 'selected hover' : ''">
                        {{job}}
                    </li>
                </ul>
            </div>
            <div class="col-9">
                <span v-if="selectedJob == 'Iconsulting SpA'">
                    <p><span class="note"><b>Role:</b></span> Business Analytics Specialist</p>
                    <p>
                        <span class="note"><b>Job Description:</b></span>
                        <span>
                            I was responsible for developing interactive dashboards and web applications that communicated with the back end via REST APIs. Each solution was tailored to the client's needs and implemented using modern, state-of-the-art technologies.<br><br>
                            I had the opportunity to work on projects for clients operating, among others, in the automotive and energy-supply sectors, supporting them in developing internal solutions for data analysis and performance evaluation of their components and products, as well as external customer-facing interfaces.
                        </span>
                    </p>
                    <p>
                        <span>
                            To develop the more complex frontend projects, I primarily relied on frameworks such as <span class="note">Angular and React</span>, while for smaller-scale projects I used <span class="note">Vue.js</span>, all supported by a solid TypeScript foundation. Backend was usually built with <span class="note">Python</span> supported by diffent suitable libraries.
                        </span>
                    </p>
                    <p>
                        My job position was fully remote, and the entire workflow was managed through <span class="note">agile project-management practices</span>, integrating individual tasks within the team and optimizing the sprints that structured the project's development.
                    </p>
                    <p>
                        <span class="note"><b>About the Company:</b></span> <a href="https://www.iconsulting.biz/" class="link-personalization" alt="iconsulting website" target="_blank">Check the website</a>
                    </p>
                </span>
                <span v-if="selectedJob == 'Netrising'">
                    <p><span class="note"><b>Role:</b></span> Full Stack Web Developer</p>
                    <p>
                        <span class="note"><b>Job Description:</b></span>
                        <span>
                           I worked primarily as a full-stack web developer, supporting both local clients and high-profile accounts, and I also developed the company's own website. <br>
                           Here is where I first approached <span class="note">WordPress</span>, although I later specialized in Angular. To support the company's long-standing and most prestigious clients, I mainly worked with <span class="note">JavaScript and Ionic</span>, optimizing their internal management software. <br><br>
                           In line with the agency's collaborative approach, I worked closely with the graphic and photography teams, developing creative solutions for client-facing visual interfaces.
                        </span>
                    </p>
                    <p>
                        Although most of the work was carried out on site, I had the opportunity to adopt <span class="note">agile project-management practices</span>, integrating individual tasks within the team and optimizing the sprints that structured the project workflow.
                    </p>
                    <p>
                        <span class="note"><b>About the Company:</b></span> <a href="https://www.netrising.com/" class="link-personalization" alt="netrising website" target="_blank">Check the website</a>
                    </p>
                </span>
            </div>    
        </div>
    </div>
</template>

<script>
export default {
    data : function(){
        return {
            jobs : ['Iconsulting SpA' , 'Netrising'],
            selectedJob : 'Iconsulting SpA',
        }
    },
    methods :{
        setCurrentJob(clicked){
            this.selectedJob = clicked
            if(clicked == 'Netrising'){
                this.counterJob = 1
            }
            else{
                this.counterJob = 0
            }
            
        },
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/skill-to-md.scss';
    .note{
        color: var(--note);
    }
    .link-personalization{
        color: var(--light);
    }
</style>
