

<template>
  <div class="fixed w-full h-full bg-red-400">

    <div class=" ">
      
      <TWrapper :map="{
        target: 1,
         showTime: 1,
        startCount: 0.4,
        position: {
          left: 45, bottom: 45
        },
        zindex: 50,
        
      }">
      </TWrapper>
      <TWrapper :map="{
        target: 2,
        showTime: 1.2,
        startCount: 0.5,
        position: {
          left: 45, bottom: 22
        },
        zindex: 49
      }">

      </TWrapper>

      <TWrapper :map="{
        target: 3,
        showTime: 1.5,
        startCount: 0.6,
        position: {
          left: 58, bottom: 65
        },
        zindex: 48
      }">

      </TWrapper>
      <TWrapper :map="{
        target: 4,
        showTime: 1.8,
        startCount: 0.6,
        position: {
          left: 58, bottom: 75
        },
        zindex: 47
      }">

      </TWrapper>
        <TWrapper :map="{
        target: 5,
        showTime: 2.5,
        startCount: 0.6,
        position: {
          left: 58, bottom: 45
        },
        zindex: 46
      }">

      </TWrapper>

    <TWrapper :map="{
        target: 6,
        showTime: 3,
        startCount: 0.3,
        position: {
          left: 70, bottom: 45
        },
        zindex: 46
      }">

      </TWrapper>
      
      
    </div>

  </div>

</template>
<script setup lang="ts">
import { ref } from "vue"
import TWrapper from "./wrapper/TWrapper.vue"


</script>
