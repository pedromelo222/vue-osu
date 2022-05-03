<template>
<div v-show="isTimeShow" class="absolute flex justify-center items-center "  :class="[isTimeLeave? 'fade-out': 'fade-in']"   
    :style="[
        `bottom: ${map.position.bottom}%;`,
        `left: ${map.position.left}%;`,
        `z-index: ${map.zindex}`
        ]">

 <!-- <div class="wrapper rounded-full border-2 border-blue-400 flex justify-center items-center ">
    <div class=" h-8 w-8 ">           
    </div></div>  -->

<svg height="100" width="100" class="wrapper absolute stroke-white">
  <circle cx="50" cy="50" r="40"  stroke-width="3" fill="none" />
</svg>
 <TRounded :target-number="map.target"></TRounded>
 </div>
 
</template>
<script setup lang="ts">
import { ref } from "vue"

import TRounded from "../target/TRounded.vue"
const props = defineProps([ 'map'])

const anim = {
    'animation-delay': `${props.map.startCount}s`
}

const isTimeShow = ref(false)
const isTimeLeave = ref(false)

setTimeout(() => {
    isTimeShow.value = true;
}, props.map.showTime * 1000);

setTimeout(() => {
        isTimeLeave.value = true;
        console.log('saiu')

}, (props.map.startCount+props.map.showTime+0.9) * 1000);

</script>

<style scoped>
.wrapper {
    transform: scale(5);
      animation: scaled 1s;
        animation-timing-function:linear;
        animation-delay: v-bind("anim['animation-delay']");
       animation-fill-mode:forwards;
       opacity: 0.5;
     
} 
@keyframes scaled {
  0%, 100%{
      opacity: 1;
  }
  0% {
    transform: scale(5);
    opacity: 1;
    
  }
  100% {
    transform: scale(1);
  }
}

.fade-in {
	opacity: 1;
	animation-name: fadeInOpacity;
	animation-timing-function: ease-in;
	animation-duration: 0.2s;
}

@keyframes fadeInOpacity {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}


.fade-out {
	opacity: 0;
	animation-name: fadeOutOpacity;
	animation-timing-function: ease-in;
	animation-duration: 0.2s;
}

@keyframes fadeOutOpacity {
	0% {
		opacity: 1;
	}
	100% {
		opacity: 0;
	}
}


</style>