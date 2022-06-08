<template>
  <div class="overflow-hidden" id="app">
    <div :class="isDark ? 'dark' : ''">
    <div class="bg-white text-black dark:bg-[black] dark:text-white flex-col ">
      <button class="w-full flex justify-end">
      
      <div class="w-auto  px-2 " @click="isDark = !isDark">
        <div v-if="isDark"> <i class="fa fa-moon-o text-3xl" aria-hidden="true"></i></div>  
        <div v-else><i class="fa fa-sun-o text-3xl" aria-hidden="true"></i> </div>
      </div>
      </button>
      <!-- <Toggle @click="isDark = !isDark" :isDark="isDark"/> -->
    <router-view/>

    </div>
    </div>
  </div>
</template>

<script>
import Toggle from './components/Toggle.vue'
export default {
    data() {
        return {
            isDark: false
        };
    },
    
    components: { Toggle }
}
</script>


<style>

@font-face{
  font-family: "space-grotesk";
  src: local("space-grotesk"),
  url(../fonts/SpaceGrotesk-VariableFont_wght.ttf) format("truetype");
}

@font-face{
  font-family: "neuzeit-grotesk";
  src: local("space-grotesk"),
  url(../fonts/NeuzeitSBook.ttf) format("truetype");
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: "space-grotesk";
 
}

</style>
