<script setup>
import {ref, defineProps } from 'vue'


const props = defineProps({
CardsDesc: {
    type: Array,
    required: true
}
});

const styleType = ref('Style1');

// const prop

</script>

<template>
    <!-- 樣式1 -->
    <div v-if="styleType=='Style1'" >
        <div class="cipherlab-cards" v-for="(desc,index) in CardsDesc" :key="index">
            <img :src="desc.src" :alt="desc.alt|| '' ">
            <h4>{{ desc.title }}</h4>
        </div>
    </div>
    <!-- 樣式2 -->
    <div v-else-if="styleType=='Style2'">
        <div class="cipherlab-cards" v-for="(desc,index) in CardsDesc" :key="index">
            <h4>{{ desc.title }}</h4>
            <img :src="desc.src" :alt="desc.alt|| '' ">
            <p>幹</p>
            <div>幹幹幹</div>
        </div>
    </div>
    
</template>

<style scoped>

.cipherlab-cards{
    background: #fff;
    overflow: auto;
    border-radius: 10px;
    margin: 20px auto;
}

.cipherlab-cards img{
    width: 100%;
}

.cipherlab-cards h4{
    padding: 0 10px 20px;
    margin: 0;
    font-size: 26px;
}

</style>