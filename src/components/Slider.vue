<script setup>
import { ref, defineProps } from 'vue'


const props = defineProps({
ImagesData: {
    type: Array,
    required: true
}
});

//當前選中的圖片索引
const currentIndex = ref(0);
const translateNum = ref(0);

const handleImageIndex = (ind) =>{
    translateNum.value = -100 * ind;
    console.log(translateNum);
}

setTimeout(handleImageIndex(translateNum),1000)

</script>

<template>
  <div class="cipherlab-background-slider">
    <div class="cipherlab-long" :style="{transform: `translateX(${translateNum}%)`}" >
        <div v-for="(image,index) in ImagesData" :class="['cipherlab-background-slider-image', `cipherlab-background-slider-image${index + 1}`]" :key="index" :id="image.id">
        <img :src="image.src" :alt="image.alt|| '' ">
    </div>
    </div>
    <div class="cipherlab-background-inputRadioBox">
        <div class="cipherlab-background-inputRadio" v-for="(image, index) in ImagesData" :key="index">
            <input type="radio" name="slider" @click="() => handleImageIndex(index)" :checked="index == 0 ? true : false ">
            <label :for="image.id"></label>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cipherlab-background-slider{
    width: 100vw;
    height: 280px;
    background: #a0a0a0;
    position: relative;
    top: 0px;
    right: 0;
    margin: auto;
    overflow: hidden;
}

.cipherlab-long{
    display: flex;
    width: 100vw;
    height: 100%;
    left: 0%;
    position: absolute;
    transform: translateX(0%);
    transition-duration: .4s;    
}

.cipherlab-background-slider .cipherlab-background-slider-image{
    width: 100%;
    height: 100%;
}

.cipherlab-background-slider-image img{
    height: 100%;
}

.cipherlab-background-inputRadioBox{
    position: absolute;
    bottom: 10px;
    right: 0;
    left: 0;
    margin: auto;
    display: flex;
    justify-content: center;
}

.cipherlab-background-inputRadio{
    width: 20px;
    height: 20px;
    padding: 0 10px;
}

.cipherlab-background-inputRadio input[type="radio"]{
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
}



/* translateX(-100%) */


input:checked + label + .cipherlab-background-slider-image {
    transform: translateX(0);
    opacity: 1;
}

input:checked ~ .cipherlab-background-slider-image {
    transform: translateX(100%);
}

</style>