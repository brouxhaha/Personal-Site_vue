<template>
    <div>
        <div class="panel panel--odd">
            <h2 class="panel__heading">Work</h2>
            <div class="wrapper">
                <div class="work grid--work">
                    <div class="work__text">
                        <p>My work is a combination of design and development. Outside a few cases, I have designed every site I have developed. I focus on creating user-friendly designs that aim to accomplish the client’s goals. </p>
                        <p>I utilize the latest HTML and CSS while adding JavaScript for interactivity and functionality. I use the latest, greatest CSS with fallbacks for browsers that need them.</p>
                    </div>
                    <div class="project--main">
                        <div class="project--main__image">
                            <router-link :to="{ name: 'project', params: {id: `${projects[0].id}`, projectIndex: index}}" class="link-block project__link">
                                <img :src="projects[0].homeImg" class="project__img">
                                <h3 class="project__name">
                                    {{ projects[0].name }}
                                </h3>
                            </router-link>
                        </div>
                    </div>

                    <div class="projects grid--projects">
                        <div class="project__item" v-for="(project, index) in projects.slice(1)" :key="index">
                            <router-link :to="{ path: `/projects/${project.id}`, params: {index: index}}" class="project__link link-block">
                                <img :src="project.homeImg" class="project__img">
                                <h3 class="project__name">
                                    {{ project.name }}
                                </h3>
                            </router-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="panel panel--even">
            <h2 class="panel__heading">Current</h2>
            <div class="wrapper">
                <div class="current grid--current">
                    <div class="learning">
                        <h3 class="panel__subheading">Learning</h3>
                        <p>I am constantly looking to improve myself as both a developer and designer. Lately, it's been mostly on the dev side, JavaScript in particular, that I've been putting my focus. I recently finished a few JavaScript courses to help improve my development knowledge and am in the middle of a third:</p>
                        <ul>
                            <li><a href="https://javascript30.com">JavaScript30</a></li>
                            <li><a href="https://learnnode.com">LearnNode</a></li>
                            <li><a href="https://www.udemy.com/vuejs-2-the-complete-guide/">Vue JS 2 - The Complete Course</a></li>
                        </ul>
                        <p>I decided I needed to learn a JS framework, and I decided on Vue because it both looked interesting and like an easier place to begin.</p>
                    </div>
                    <div class="projects">
                        <h3 class="panel__subheading">Projects</h3>
                        <p>Like everyone, I have at least a couple projects to work on, both to reinforce my learning and to see what I can come up with. This site is the perfect example, as it is built in Vue.js to utilize the skills I've learned in the Vue.js course I am currently working through. </p>
                        <p>It's been a while since I've worked on them, but I have a couple app ideas I intend to continue building in order to support and strengthen my Node.js knowledge:</p>
                        <ul>
                            <li>A recipe app</li>
                            <li>A family photo album app</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <!--<Projects></Projects>-->
</template>

<script>
    /*import Projects from './components/projects/Projects.vue';*/
    
    export default {
         computed: {
            projects() {
                return this.$store.state.projects;
            } 
         }/*
        data() {
            return {
                projects: [
                    {
                        id: 'travel-alaska',
                        name: 'State of Alaska & Alaska Travel Industry Association',
                        description: '',
                        homeImg: '/src/assets/travel-alaska_initial_2000x1200.jpg'
                    },
                    {
                        id: 'anchorage-library',
                        name: 'Anchorage Public Library',
                        description: '',
                        homeImg: '/src/assets/anchorage-library_initial_2000x1200.jpg'
                    },
                    {
                        id: 'visit-ketchikan',
                        name: 'City of Ketchikan',
                        description: '',
                        homeImg: '/src/assets/visit-ketchikan_initial_2000x1200.jpg'
                    },
                    {
                        id: 'anchorage-museum',
                        name: 'Anchorage Museum',
                        description: '',
                        homeImg: '/src/assets/anchorage-museum_initial_2000x1200.jpg'
                    }
                ]
            }
        }*/
        /*components: {
            Projects: Projects
        }*/
    }
</script>

<style lang="sass">
    $black: #282828;
    $main-cool: #151e30;
    $main-warm: #ff9600;
    $alt-cool: #2a7f70;

    body {
        color: white;
    }

    .panel--main {
        background: rgba($main-cool, 0.75);
    }

    .panel {
        padding-top: 70px;
        padding-bottom: 150px;
    }

    .panel--odd {
        background: rgb(21,30,48);
        background: linear-gradient(180deg, rgba(21,30,48,0.75) 0%, rgba(42,127,112,0.75) 100%);
        min-height: 500px;
    }

    .panel--even {
        background: rgb(21,30,48);
        background: linear-gradient(180deg, rgba(42,127,112,0.75) 0%, rgba(21,30,48,0.75) 100%);
    }

    .panel__heading {
        font-size: 2.5rem;
        font-weight: 900;
        line-height: 1;
        letter-spacing: -3px;
        color: rgba(white, 0.5);
        text-transform: uppercase;
        margin-top: 0;
        position: relative;
        padding-left: 5%;
        margin-bottom: 2rem;

        @media (min-width: 600px){
            font-size: 4rem;
            line-height: 0.85;
            letter-spacing: -5px;
        }

        &:after {
            content: '';
            height: 6px;
            width: 55%;
            background: $main-warm;
            //background: linear-gradient(90deg, #ff9600 32.15%, transparent 32.15%, transparent 35.37%, #ff9600 35.37%, #ff9600 40.19%, transparent 40.19%, transparent 42.12%, #ff9600 42.12%, #ff9600 45.34%, transparent 45.34%, transparent 46.62%, #ff9600 46.62%, #ff9600 48.23%, transparent 48.23%, transparent 49.04%, #ff9600 49.04%, #ff9600 50%, #ff9600 50%, #ff9600 82.15%, transparent 82.15%, transparent 85.37%, #ff9600 85.37%, #ff9600 90.19%, transparent 90.19%, transparent 92.12%, #ff9600 92.12%, #ff9600 95.34%, transparent 95.34%, transparent 96.62%, #ff9600 96.62%, #ff9600 98.23%, transparent 98.23%, transparent 99.04%, #ff9600 99.04%, #ff9600 100%) no-repeat left center;
background: rgb(255,150,0);
background: linear-gradient(90deg, rgba(255,150,0,1) 0%, rgba(255,150,0,1) 60%, rgba(255,150,0,0) 60%, rgba(255,150,0,0) 65%, rgba(255,150,0,1) 65%, rgba(255,150,0,1) 75%, rgba(255,150,0,0) 75%, rgba(255,150,0,0) 79%, rgba(255,150,0,1) 79%, rgba(255,150,0,1) 87%, rgba(255,150,0,0) 87%, rgba(255,150,0,0) 90%, rgba(255,150,0,1) 90%, rgba(255,150,0,1) 93%, rgba(255,150,0,0) 93%, rgba(255,150,0,0) 96%, rgba(255,150,0,1) 96%, rgba(255,150,0,1) 98%, rgba(255,150,0,0) 98%);
            background-size: 100%;
            position: absolute;
            bottom: 0;
            left: 0;
            //box-shadow: 20px 0 0 3px $main-warm;
        }
    }

    .panel__subheading {
        margin-top: 0;
        margin-bottom: 0.25rem;
    }

    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 100px;
    }

    .grid--work {
        display: grid;
        grid-template-rows: auto;

        @media (min-width: 650px){
            grid-gap: 100px 50px;
            align-items: center;
        }
    }

    .grid--current {
        display: grid;
        grid-template-rows: auto;
        grid-gap: 30px;

        @media (min-width: 650px){
            grid-gap: 50px;
            grid-template-columns: 1fr 1fr;
        }
    }

    .project__item, .project--main {
        box-shadow: 0 5px 3px 0 rgba($main-cool, 0.5);
        position: relative;
    }

    .project--main {
        z-index: 3;
    }

    .project__item {
        &:first-child {
            z-index: 2;
        }

        &:nth-child(2) {
            z-index: 1;
        }

        &:nth-child(3) {
            z-index: 0;
        }
    }

    @media (min-width: 650px){
        .work__text {
            grid-column: 1 / 4;
        }

        .project--main {
            grid-column: 4 / 7;
            box-shadow: 0 3px 3px 0 rgba($main-cool, 0.5);
        }

        .grid--projects {
            display: grid;
            grid-column: 1 / 7;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 0;
        }
    
        .project--main__image {
            position: relative;

            &:after {
                content: '';
                width: 1px;
                height: 70%;
                position: absolute;
                left: -25px;
                top: 50%;
                transform: translateY(-50%);
                background: var(--main-warm);
            }
        }
    
        .project__item {
            box-shadow: 5px 0 3px 0 rgba($main-cool, 0.5);
            position: relative;

            &:first-child {
                z-index: 2;
            }

            &:nth-child(2) {
                z-index: 1;
            }

            &:nth-child(3) {
                z-index: 0;
            }
        }
    }

    .project__name {
        font-size: 1.25rem;
        font-weight: normal;
        line-height: 1;
        color: white;
        text-align: center;
        position: absolute;
        width: 90%;
        top: 50%;
        left: 5%;
        transform: translateY(-50%);
        margin: 0;
        text-shadow: 0 1px 6px rgba($black, 0.5);

        &:after {
            content: '';
            height: 3px;
            width: 100%;
            position: absolute;
            bottom: -10px;
            background: var(--main-warm);
            left: 50%;
            transform: translateX(-50%) scaleX(0.25);
            transition: transform 0.25s ease;
        }
    }
    
    .project__img {
        display: block;
    }

    .project__link {
        &:before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background: linear-gradient(180deg, rgba($main-cool, 0) 0%, rgba($main-cool, 1) 100%);
        }

        &:hover .project__name:after {
            transform: translateX(-50%) scaleX(1);
        }
    }

    .spacing {
        margin-bottom: 5rem;
    }

    .link-block {
        display: block;
    }
</style>
