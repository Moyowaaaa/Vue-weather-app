<template>
<div class="h-screen  flex flex-col ">
    <router-link to="/">
    <div class="flex w-auto px-2 sign text-3xl pl-[4rem] cursor-pointer">
        &larr;
    </div>
    </router-link>  
    

    <div class="text-center flex flex-col items-center justify-center h-full text-[1.5rem]">
    <h2>{{weather.name}}, {{weather.sys.country}}</h2>
    <br/>
    
    <h4>{{weather.weather[0].description}}</h4>

    <div>
    <img :src="`${url}`" />
    </div>

    <p>Wind speed: {{weather.wind.speed }} mph</p>
    <!-- <weather-card :data="weather" /> -->

    <!-- <h2>{{weather.name}}</h2>
    <p>{{weather.coord.lon}}</p> -->
    </div>  
</div>


</template>

<script>
// import WeatherCardVue from '@/components/WeatherCard.vue'
import WeatherCard from '@/components/WeatherCard.vue'

export default {

  components: { WeatherCard },
    name:'Weather',


    data() {
        return {
            weather: '',
            url:''
        }
    },
    mounted () {
        const response = (JSON.parse(localStorage.getItem('weather')))
       this.weather = response

       const url = `https://openweathermap.org/img/wn/${response.weather[0].icon}` + '@2x.png'
       this.url = url
       
    }
}
</script>


<style scoped>
.sign{
    animation: bounce 1s infinite;
    animation-duration: 1s;
  animation-delay: -2s;
  animation-iteration-count: 10;

@keyframes bounce {
  0%, 100% {
    transform: translateY(-25%);
    animation-timing-function: cubic-bezier(0.8, 0, 1, 1);
  }
  50% {
    transform: translateY(0);
    animation-timing-function: cubic-bezier(0, 0, 0.2, 1);
  }
}
}
</style>


