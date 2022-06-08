<template>
<div class="w-screen  h-screen flex flex-col items-center font-space-grotesk dark:bg-[black] dark:text-white">
  <div class="w-10/12  flex flex-col h-full items-center lg:w-4/12">


    <div class="w-full flex flex-col items-center justify-center h-full">
      <label class="font-space-grotesk">Weather App</label>
      <br>
      <input type="text" v-model="city" placeholder="Enter City Name" class="w-10/12 px-2 py-4 border-b-2 text-black  focus:border-b-2 focus:border-[black] dark:border-[white] dark:bg-black dark:text-white outline-none">
      <button class="bg-black text-white my-12 px-4 w-7/12 py-2 outline-none border-2 border-[white] " @click="checkWeather">Search</button>
      </div>

  </div>
</div>
</template>

<script>
// import axios from 'axios';

import axios from 'axios';
import router from 'vue-router'

export default {
  data() {
    return {
      city:''
    }
  },
  mounted() {
    // this.checkWeather()
   localStorage.clear();
   
  },
  methods: {
   getWeather() {
     console.log(this.city)
//  router.push('/about/')
   },
  async checkWeather () {
     
        try {
          const city = this.city;
          const response = await axios.get("https://api.openweathermap.org/data/2.5/weather?q=" +
    city + "&appid=e501511406daf37725e99b00cf9e08bb")

    localStorage.setItem('weather', JSON.stringify(response.data));
        } catch (error) {
            console.log(error)
        }
        this.$router.push('/weather')
          
        }
  }
  }






</script>


