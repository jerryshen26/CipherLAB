<script setup>
import HelloWorld from './components/HelloWorld.vue'
import HeaderMenu from './components/Header.vue'
import Slider from './components/Slider.vue'
import SolutionsCard from './components/Card.vue'


const SliderImages = [
  {src : "Home/op-240417-03213.jpg", id : "home-trigger1"},
  {src : "Home/op-240513-04053.jpg", id : "home-trigger2"},
  {src : "Home/op-231011-05041.webp", id : "home-trigger3"},
  {src : "Home/op-231116-07617.webp", id : "home-trigger4"}];

const SolutionsCards = [
  {src : "Solutions/op-221028-09764.jpg", title : "Warehousing", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "Transportation And Logistics", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "Retail", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "ManufacturingHealthcare", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "Healthcare", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "Field Mobility", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "Government", desc : ""},
  {src : "Solutions/op-221028-09764.jpg", title : "ReMoFactory", desc : ""},



]

const getImagesSrc = (src) =>{
    return new URL(`./images/${src}`, import.meta.url).href;
}

SliderImages.forEach(image=>{
  image.src = getImagesSrc(image.src);
});

SolutionsCards.forEach(image=>{
  image.src = getImagesSrc(image.src);
});



</script>

<template>
  
  <HeaderMenu />
  <div class="cipherlab-block" style="margin-top: 76px;"></div>
  <Slider :ImagesData= "SliderImages"/>
  <div class="cipherlab-background">
    <h3>Industry Solutions</h3>
    <a href="#" class="cipherlab-viewMore">
      <span>view more</span>
      <span><img src="./images/Home/ep_arrow-right.svg" alt=""></span>
    </a>
    <SolutionsCard :CardsDesc="SolutionsCards" :styleType="Style1" />
  </div>


</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.cipherlab-background{
  padding: 20px 20px 40px;
  background: black;
  width: 100vw;
  box-sizing: border-box;
}
.cipherlab-background h3{
  color: white;
  font-size: 30px;
  margin: 10px 0;
}
.cipherlab-background a{
  margin: 10px 0 20px;
  color: white;
}
.cipherlab-viewMore{

}

.cipherlab-viewMore img{
  padding: 5px;
}

.cipherlab-viewMore span,.cipherlab-viewMore img{
  font-size: 20px;
  vertical-align: middle;
}

</style>
