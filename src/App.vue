<template>
    <div class="container">
        <div class="panel--main relative">
            <!--<img src="./assets/triangle.svg" class="header__svg">--> 
            <div class="header__svg"> 
                <svg width="100%" viewBox="0 0 1401 568" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 0L700 568C933.5 379 1389.6 0 1400 0H0Z" transform="translate(0.5)" fill="url(#paint0_linear)" fill-opacity="0.6"/>
                <defs>
                    <linearGradient id="paint0_linear" x2="1" gradientUnits="userSpaceOnUse" gradientTransform="translate(1002.5 1080.95) scale(625 1538.9) rotate(180)">
                    <stop stop-color="#FF9600"/>
                    <stop offset="1" stop-color="#2A7F70"/>
                    </linearGradient>
                </defs>
                <g class="svg__line-group">
                    <line x1="140" y1="113" x2="253" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />   
                    <line x1="150" y1="121" x2="271" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="160" y1="129" x2="289" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="170" y1="137" x2="307" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                </g>
                
                <g class="svg__line-group">
                    <line x1="320" y1="259" x2="579" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />   
                    <line x1="330" y1="267" x2="597" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="340" y1="275" x2="615" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="350" y1="283" x2="633" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                </g>
                
                
                <g class="svg__line-group">
                    <line x1="480" y1="389" x2="869" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />   
                    <line x1="490" y1="397" x2="887" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="500" y1="404" x2="904" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="510" y1="412" x2="922" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                </g>
                <g class="svg__line-group">
                    <line x1="640" y1="518" x2="1158" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="650" y1="526" x2="1176" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="660" y1="534" x2="1194" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                    <line x1="670" y1="543" x2="1213" y2="0" stroke="#151e30" stroke-width="2" class="svg__line" />
                </g>  
            </svg>
            </div>

            <app-header></app-header>
            <div class="wrapper relative">
                <transition name="grow" mode="out-in">
                    <router-view name="main-panel"></router-view>
                </transition>
            </div>
        </div>
        <main class="content--main">
            <transition name="fade" mode="out-in">
                <router-view></router-view>
            </transition>
        </main>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import Footer from './components/Footer.vue';

    export default {
        components: {
            appHeader: Header,
            appFooter: Footer
        }
    }
</script>

<style lang="sass">
    @import './scss/reset.scss';

    p {
        margin-top: 0;
    }

    .header__svg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        max-height: 100%;
    }

    .fade-enter {
        opacity: 0;
    }

    .fade-enter-active {
        animation: fade-in 0.2s ease-in forwards;
    }

    .fade-leave {
        opacity: 1;
    }

    .fade-leave-active {
        animation: fade-out 0.2s ease-out forwards;
    }

    .grow-enter {
        transform: scale(0);
    }

    .grow-enter-active {
        animation: grow-in 0.2s ease-in forwards;
    }

    .grow-leave {
        transform: scale(1);
        transform-origin: 50%;
    }

    .grow-leave-active {
        animation: grow-out 0.2s ease-out forwards;
    }

    @keyframes fade-in {
        from {
            opacity: 0;
        }

        to {
            opacity: 1;
        }
    }

    @keyframes fade-out {
        from {
            opacity: 1;
        }
        
        to {
            opacity: 0;
        }
    }

    @keyframes grow-in {
        from {
            transform: scale(0);
        }

        to {
            transform: scale(1);
        }
    }

    @keyframes grow-out {
        from {
            transform: scale(1);
        }
        
        to {
            transform: scale(0);
        }
    }

/* #Site Specific
================================================== */
$black: #282828;
$main-cool: #151e30;
$main-warm: #ff9600;
$alt-cool: #2a7f70;

html {
    --black: #282828;
    --main-warm: #FF9600;
    --main-cool: #151E30;
    --alt-cool: #2A7F70;
    font-family: 'motiva-sans';
    color: var(--black);
    line-height: 1.4;
}

body {
    font-size: 1rem;

    @media (min-width: 950px){
        font-size: 1.25rem;
    }
}

a {
    text-decoration: none;
    color: var(--main-warm);
    position: relative;
    -webkit-transition: all .25s ease-in;
    transition: all .25s ease-in;
    font-weight: bold;

    &:hover {
        color: lighten($main-warm, 20%);
    }
}

img {
    width: auto;
    height: auto;
    max-width: 100%;
}

.wrapper {
    margin: 0 auto;
    width: 90%;
    max-width: 1500px;
}

.relative {
    position: relative;
}

.svg__line {
  opacity: 0.25;
}
</style>