

<template>
    <div @click="onTargetClick()" class="absolute flex justify-center items-center rounded-full  bg-white border-1  h-39 w-39 transition-opacity select-none">
  <div ref="target" class="flex   justify-center items-center p-2 rounded-full bg-blue-500 h-35 w-35">
    <div class="font-semibold text-5xl text-white">
        {{targetNumber}}
      </div>
      
  </div>
</div>

</template>
<script setup lang="ts">
import { reactive, ref } from "vue"
import { useMouse } from '@vueuse/core'
const props = defineProps([ 'targetNumber'])
const target = ref<HTMLElement | null>(null);
const { x, y } = useMouse()

const clickPosition = reactive({
  x: 0,
  y: 0,
})
function onTargetClick(){
  const bounds = target.value?.getBoundingClientRect()
  clickPosition.x = x.value - (bounds?.left !== undefined? bounds?.left : 0 as any)
  clickPosition.y = y.value - (bounds?.top !== undefined? bounds?.top : 0 as any)
  console.log(clickPosition)
  
}
</script>
