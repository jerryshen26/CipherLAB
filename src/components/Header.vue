<script setup>
import { ref } from 'vue'

defineProps({

})
const displayView = ref("none");

const handleClick = () => {
  displayView.value = displayView.value === "none" ? "block" : "none";
}
</script>

<template>
    <header>
        <div class="cipherlab-menu-close">
            <div class="cipherlab-menu-left-Func">
                <img class="cipherlab-menu-cancleImg" src="../images/menu.svg" alt="" @click="handleClick">
            </div>
            <div class="cipherlab-menu-center-Func">
                <img src="../images/cipherlab.svg" alt="">
            </div>
            <div class="cipherlab-menu-right-Func">
                <img src="../images/translate.svg" alt="">                            
                <img src="../images/search.svg" alt="">
            </div>
        </div>
        <div class="cipherlab-menu-open" :style="{ display: displayView }">
            <img class="cipherlab-menu-cancleImg" src="../images/cancel.svg" alt="" @click="handleClick">
            <ul>
                <li>
                    <a href="#">Home</a>
                </li>
                <li>
                    <a href="#">Industry Solutions</a>
                </li>
                <li>
                    <a href="#">Products</a>
                </li>
                <li>
                    <a href="#">Support and Services</a>
                </li>
                <li>
                    <a href="#">Partners</a>
                </li>
                <li>
                    <a href="#">News Room</a>
                </li>
                <li>
                    <a href="#">About Us</a>
                </li>
                <li>
                    <a href="#">Investor Relations</a>
                </li>
            </ul>
        </div>
    </header>
</template>

<style scoped>

header{
    position: fixed;
    width: 100%;
    height: auto;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    display: table;
    z-index: 1000;
    box-shadow: 0 0 3px 0px #2e2e2e80;
    background: #fff;
}

header .cipherlab-menu-close{
    padding: 15px;
    position: relative;
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;
    align-items: center;
}

header .cipherlab-menu-open{
    background: #000;
    width: 100%;
    height: 100vh;
    position: absolute;
    box-sizing: border-box;
    padding: 20px 15px;
    top: 0;
}

header .cipherlab-menu-open ul{
    display: flex;
    flex-direction: column;
    text-align: center;
    padding: 0;
}


header .cipherlab-menu-open ul li{
    padding: 10px 5%;
    text-align: start;
    color: #fff;
}

header .cipherlab-menu-open ul li a{
    color: white;
}

header .cipherlab-menu-open .cipherlab-menu-cancleImg{
    
}

.cipherlab-menu-left-Func,.cipherlab-menu-right-Func{
    display: flex;
    position: relative;
    align-items: center;
}

.cipherlab-menu-left-Func{
    width: 36px;
    height: 36px;
}



.cipherlab-menu-left-Func img,.cipherlab-menu-right-Func img{
    width: 36px;
}






</style>

