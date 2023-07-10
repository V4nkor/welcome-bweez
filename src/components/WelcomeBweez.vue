<template>
    <video ref="backgroundVideo" src="/videos/code.mov" autoplay muted loop id="myVideo">
        <!-- <source src="/video/matrix720.mp4" type="video/mov"> -->
    </video>
    <div ref="page1" :class="`center transition page1 ${index === 1 ? 'show' : 'hidden'}`">
        <div @click="nextPage" class="clickable content">
            <h1><span :class="`${terminal === 1 ? 'terminal' : 'notTerminal'}`">></span>Hello world !</h1>
            Ce site est un exercice d'apprentissage de vue.js dans le cadre d'un entretient d'alternance pour mon année 2023-2025 en Master Développement chez Sup de Vinci<br><br>
            <span>>Click Me !&lt;</span>
        </div>
    </div>
    <div ref="page2" :class="`center transition page2 ${index === 2 ? 'show' : 'hidden'}`">
        <div class="content">
            <h1>Qui suis-je ?</h1>
            <img src="images/mathieu.png">
            <p>
                Mathieu MORGAT, etudiant à l'IUT d'Orsay en Licence Professionelle PRISM. <br>
                Je souhaite poursuivre mes études en informatique à Sup de Vinci pour un master de deux ans.
                <br><br>
                Vous pourrez accéder à mon portfolio : <a target="blank" href="https://mmorgat.ydns.eu">Portfolio Web</a><br><br>
                Mon CV Sup de Vinci: <a target="blank" href="PDF/cv-mathieu-morgat.pdf">CV</a><br><br>
                Ainsi qu'à mon github : <a target="blank" href="https://github.com/V4nkor">Profil Github</a> <br>
            </p>
            <span @click="previousPage" class="clickable bigArrow">	&larrhk;</span><span @click="nextPage" class="clickable bigArrow">&rarrhk;</span>
        </div>
    </div>
    <div ref="page3" :class="`center transition page3 ${index === 3 ? 'show' : 'hidden'}`">
        <div class="content">
            <div class="scrollable">
                <h1>Projets personnels :</h1><br>
                En dehors des cours et de mes expériences professionelles, j'ai pu effectuer des projets personnels pour apprendre divers aspects de l'informatique et expérimenter : <br><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/piweb.jpg">
                        <h4>Piweb</h4>
                        <p>Hébergement maison de mon portfolio web sur une raspberry pi</p>
                        <span>Status : Refonte Contenu - <a target="blank" href="https://mmorgat.ydns.eu">Hébergé</a></span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/odroid.jpg">
                        <h4>NAS Odroid HC4</h4>
                        <p>Serveur de stockage NAS sous openmediavault créé sur une Odroid HC4 sous armbian</p>
                        <span>Status : En cours d'utilisation</span>
                    </div>
                </div><br>
                <h1>Exercices Scolaires</h1><br>
                Lors de ma licence professionelle, j'ai pu à de nombreuses reprises participer 
                à des projets de développement web ou mobileen groupes ou seul, en voici quelques uns : <br><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png"><br><br>
                        <h4>Projet GAPM</h4>
                        <p>Projet de fin d'année. Site de RDV médicaux</p>
                        <span>Status : Finis - Hébergé Privé</span><br>
                        <a target="blank" href="PDF/GAPM - Cahier des charges.pdf">Rapport de rendu</a>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/pendix.png">
                        <h4>Projet Pendix</h4>
                        <p>Projet IOS de jeu du Pendu</p>
                        <span>Status : Finis</span><br>
                        <a target="blank" href="PDF/DOC IOS.pdf">Rapport de rendu</a>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/cristo.png">
                        <h4>Projet Cristo</h4>
                        <p>Projet de reconnaissance vocale en IHM</p>
                        <span>Status : Ebauche - Non hébergé</span><br>
                        <a target="blank" href="PDF/Cristo.pdf">Rapport de rendu</a>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/webpizza.png">
                        <h4>TP webpizza</h4>
                        <p>Projet sous DJango de pizza</p>
                        <span>Status : Ebauche - <a target="blank" href="http://mmorgat.projects.ydns.eu:3000/">Hébergé</a></span>
                    </div>
                </div><br>
                <h1>Expériences Professionelles</h1><br>
                En tant que stagiaire puis alternant, j'ai travaillé sur des projets ancrés dans le monde professionnel : <br><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/dtp-ged.png">
                        <h4>Les Archives BTP</h4>
                        <p>Armoire à plan</p>
                        <span>Status : <a target="blank" href="https://dtp-ged.fr">Production - Privé</a></span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gallimedia.png">
                        <h4>Gallimedia - Scripts Bash</h4>
                        <p>Scripts bash d'automatisation de mise en place de serveurs webs et Drupal sous linux, migration de bases de données et création de documentation</p>
                        <span>Status : Finis</span>
                    </div>
                </div><br>
            </div>
            <span @click="previousPage" class="clickable bigArrow">	&larrhk;</span><span @click="nextPage" class="clickable bigArrow">&rarrlp;</span>
        </div>
    </div>
    <span class="pagination">{{index}}/3</span>
</template>

<script setup lang="ts"> //Partie setup lancée avant le HTML

import { onMounted, onUnmounted, ref, type Ref } from 'vue';

const index = ref(1); //Index des pages min = 1 max = 3

/* const page1:Ref<HTMLElement | undefined> = ref(); //Prends la ref="page1" et crée une variable
const page2:Ref<HTMLElement | undefined> = ref();
const page3:Ref<HTMLElement | undefined> = ref(); */

const backgroundVideo:Ref<HTMLElement | undefined> = ref();

const terminal = ref(1);

/* const pages:Array<Ref<HTMLElement | undefined>> = [page1,page2,page3]; */ //Array contenant toutes les pages

function nextPage(){
    index.value ++;
    if(index.value > 3){
        index.value = 1;
    }
}
function previousPage(){
    index.value --;
    if(index.value <= 0){
        index.value = 3;
    }
}

function showHideTerminal(){
    if(terminal.value === 1){
        terminal.value = 0;
    }
    else{
        terminal.value = 1;
    }
}

//onMounted lancé lorsque le template est crée
onMounted(() => {
    var w = window.innerWidth;
    var h = window.innerHeight;
    if(w > 720|| h > 1080){
        /* const video = backgroundVideo.value;
        video.src = "/video/matrix1080.mp4" */
    }
    else{

    }
    setInterval(showHideTerminal, 2000);
});

</script>

<style lang="scss">

$main-green: #07b607;
$dark-green: #002000;

.bigArrow{
    font-size: 30px;
    font-weight: bolder;
}
.bigArrow:hover{
    cursor:pointer;
    font-size: 34px;
}

.content{
    text-align: center;
    margin-top: auto;
    margin-bottom: auto;
    background-color: black;
    padding:20px;
    border-radius: 15px;
    color: $main-green;
    height: 100%;
    max-width: 800px;
}

h1{
    font-size: 30px;
    margin:0px;
}

.page1{
    .content:hover{
        cursor:pointer;
        transform: scale(1.05);
    }
}

.page2{
    img{
        width:200px;
        border-radius: 25px;
    }
}

.page3{
    .scrollable{
        max-height:700px;
    }
}

.elementGrid{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 40px;
    grid-auto-rows: minmax(100px, auto);
    padding-left:8px;
}

.elementDiv{
    transition: transform .2s; /* Animation */
    background-color: $dark-green;
    border:solid black 1px;
    width:355px;
    p{
        margin:0px;
    }
    h4{
        margin:0px;
    }
    a{
        color:#07b607;
    }
}

.elementImage{
    width: 100%;
    margin-left:auto;
    margin-right:auto;
}

.elementImage:hover {
    transform: scale(1.05);
}

.transition{
    transition: all 0.9s;
}

.pagination{
    position:absolute;
    font-size: 30px;
    bottom: 10px;
    right: 10px;
    color: $main-green;
    background-color: black;
    opacity:0.9;
    padding:10px;
    border-radius: 15px;
}

.center {
  justify-content: center;
  align-items: center;
  text-align: center;
  min-height: 90vh;
}

#myVideo {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  z-index: -1;
}

.scrollable{
    overflow-y:scroll;
}

.scrollable::-webkit-scrollbar-track
{
  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
  background-color: rgb(168, 219, 168);
}

.scrollable::-webkit-scrollbar
{
  width: 6px;
  background-color: #F5F5F5;
}

.scrollable::-webkit-scrollbar-thumb
{
  background-color: $main-green;
  border-radius: 25px;
}

.clickable:hover{
    cursor:pointer;
}

.show{
    display:flex;
    opacity:0.9;
    animation-duration: 2s;
    animation-name: showAnimation;
    img{
        opacity:1;
    }
}

.hidden{
    display:none;
    opacity:0;
    animation-duration: 2s;
    animation-name: hiddenAnimation;
}

.notTerminal{
    display:none;
    opacity:0;
}

@keyframes showAnimation {
    from {
        display:none;
        opacity:0;
    }
    to {
        display:flex;
        opacity:0.9;
    }
}

@keyframes hiddenAnimation {
    from {
        display:flex;
        opacity:0.9;
    }
    to {
        display:none;
        opacity:0;
    }
}

</style>