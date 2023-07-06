<template>
    <video ref="backgroundVideo" src="/videos/code.mov" autoplay muted loop id="myVideo">
        <!-- <source src="/video/matrix720.mp4" type="video/mov"> -->
    </video>
    <div ref="page1" :class="`center transition page1 ${index === 1 ? 'show' : 'hidden'}`">
        <div @click="nextPage" class="clickable content">
            <h1>Hello world !</h1>
            Ce site est un exercice d'apprentissage de vue.js dans le cadre d'un entretien d'alternance pour mon année 2023-2025 en Master Développement chez Sup de Vinci<br>
        </div>
    </div>
    <div ref="page2" :class="`center transition page2 ${index === 2 ? 'show' : 'hidden'}`">
        <div class="content">
            <div class="scrollable">
                <h1>Projets personnels :</h1><br>
                En dehors des cours et de mes expériences professionelles, j'ai pu effectuer des projets personnels pour apprendre divers aspects de l'informatique et expérimenter.<br><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/piweb.jpg">
                        <h4>Piweb</h4>
                        <p>Hébergement maison de mon portfolio web sur une raspberry pi</p>
                        <span>Status : Refonte Contenu - <a target="blank" href="https://mmorgat.ydns.eu">Hébergé</a></span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Pendix</h4>
                        <p>Projet IOS de jeu du Pendu</p>
                        <span>Status : Finis</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Cristo</h4>
                        <p>Projet de reconnaissance vocale en IHM</p>
                        <span>Status : Ebauche - Non hébergée</span>
                    </div>
                </div><br>
                <h1>Exercices Scolaires</h1><br>
                Lors de ma licence professionelle, j'ai pu à de nombreuses reprises participer 
                à des projets en groupes ou seul de développement web ou mobile, en voici quelques uns : <br><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet GAPM</h4>
                        <p>Projet de site de RDV médicaux</p>
                        <span>Status : Finis - Privé</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Pendix</h4>
                        <p>Projet IOS de jeu du Pendu</p>
                        <span>Status : Finis</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Cristo</h4>
                        <p>Projet de reconnaissance vocale en IHM</p>
                        <span>Status : Ebauche - Non hébergée</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>TP webpizza</h4>
                        <p>Projet sous DJango de pizza</p>
                        <span>Status : Ebauche - <a target="blank" href="http://mmorgat.ydns.eu:3000/">Hébergée</a></span>
                    </div>
                </div><br>
                <h1>Expériences Professionelles</h1><br>
                <div class="elementGrid">
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Les Archives BTP</h4>
                        <p>Armoire à plan</p>
                        <span>Status : <a target="blank" href="https://dtp-ged.fr">Prod</a></span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Pendix</h4>
                        <p>Projet IOS de jeu du Pendu</p>
                        <span>Status : Finis</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>Projet Cristo</h4>
                        <p>Projet de reconnaissance vocale en IHM</p>
                        <span>Status : Ebauche - Non hébergée</span>
                    </div>
                    <div class="elementDiv">
                        <img class="elementImage" src="/images/gapm.png">
                        <h4>TP webpizza</h4>
                        <p>Projet sous DJango de pizza</p>
                        <span>Status : <a href="http://mmorgat.ydns.eu:3000/">Ebauche - Hébergée</a></span>
                    </div>
                </div><br>
            </div>
            <span @click="nextPage" class="clickable bigArrow">&rarr;</span>
        </div>
    </div>
    <div ref="page3" :class="`center transition page3 ${index === 3 ? 'show' : 'hidden'}`">
        <div class="content">
            <h1>Pourquoi Bweez ?</h1>
            <span @click="nextPage" class="clickable bigArrow">&rarr;</span>
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

/* const pages:Array<Ref<HTMLElement | undefined>> = [page1,page2,page3]; */ //Array contenant toutes les pages

function nextPage(){
    index.value ++;
    if(index.value > 3){
        index.value = 1;
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
});

</script>

<style lang="scss">

$main-green: #07b607;
$dark-green: #002000;

.bigArrow{
    font-size: 30px;
    font-weight: bolder;
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
    }
}

.page2{
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
    cursor: pointer;
}

.transition{
    transition: all 1s;
}

.pagination{
    position:absolute;
    font-size: 30px;
    bottom: 10px;
    right: 10px;
    color: $main-green;
    background-color: black;
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
    opacity:1;
    animation-duration: 2s;
    animation-name: showAnimation
}

.hidden{
    display:none;
    opacity:0;
    animation-duration: 2s;
    animation-name: hiddenAnimation
}

@keyframes showAnimation {
    from {
        display:none;
        opacity:0;
    }
    to {
        display:flex;
        opacity:1;
    }
}

@keyframes hiddenAnimation {
    from {
        display:flex;
        opacity:1;
    }
    to {
        display:none;
        opacity:0;
    }
}

</style>