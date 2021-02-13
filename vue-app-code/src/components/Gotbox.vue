<template>
<div class="App">
 <!-- <video src='../assets/weathervid.mp4' autoPlay loop muted style="width:100%;height:auto"/> -->

  <div class="mainbox">
    <div class="searchbox">
            <div class="inputbox">
                
                <input required type="text" class="inputVal" v-model="query" placeholder="Enter City Name"/>
                <input type="submit"   class="clicksub"  @click="fetchweather" value="Search">
                
                <br>
                <!-- {{query}} -->

            </div>   
            <div v-if='typeof weather.main != "undefined" '>
            <h1 class="name" >{{weather.name}}</h1>
            <p class="desc">{{weather.weather[0].description}}</p>
            <span class="temp">{{Math.round(weather.main.temp)}}°C</span>
           
            <div id="image">
            </div><br>
            </div>
            <span id="creator" >Created by Souvik Das</span>
    </div>
    
  </div>
 
 </div> 
</template>

<script>
export default {


  name: 'Gotbox',
  props: {
    msg: String
  },
  data(){
      return {
        api_key: '7353020ee6b5ea4e932e98307c3b700e',
        url_base: 'https://api.openweathermap.org/data/2.5/',
        query: '',
        weather: {

        }
      }
  },
  methods: {
    
    fetchweather(){


      fetch(`${this.url_base}weather?q=${this.query}&units=metric&appid=${this.api_key}`)
      .then(res=> {
          return res.json()
          })
      .then(this.setResults)

    },
    setResults(results){
        this.weather = results;
    }
  }

  
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@import '../assets/weathbox.css';
@import '../assets/bootstrap.css'



</style>
