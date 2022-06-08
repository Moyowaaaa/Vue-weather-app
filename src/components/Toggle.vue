<template>
    <div class="ml-12">
            <button @click="toggleDark">
      
      <div>
        <div v-if="isDark"><i class="fa fa-moon-o" aria-hidden="true"></i></div>  
        <div v-else> Light Mode </div>
      </div>
      </button>
    </div>
</template>


<script>
export default {
    props:['isDark'],
    methods:{
        toggleDark(){
          this.$emit('isDark', !this.isDark)
        }
    }
}
</script>

<style scoped>

</style>