<template>
  <div class="container">
    <div class="About">
      <h2> <button><a href="https://nodejs-events.herokuapp.com/">
            <fa icon="bars"/>
            About Me  </a>
            </button> </h2>
    </div>
    <h1><MyHeader EventName="Guest Lecture" 
      UniversityName="University of New Haven"/> </h1>
    <MyEventbox :events="events"  />
  </div>
</template>
<script>
import MyHeader from './components/MyHeader.vue'
import MyEventbox from './components/MyEventbox.vue'
export default {
  name: 'App',
  components: {
    MyHeader,
    MyEventbox
  },
  data(){
    return {
      events: []
    }
  },
  methods: {
      async fetchevents(){
         const res= await fetch('https://nodejs-events.herokuapp.com/api')
         //const res= await fetch("http://localhost:5984/events/")
         const data= await res.json()
         console.log(data)
         return data
      }
  },
  async created(){
    this.events = await this.fetchevents()
    console.log(this.events)
  }
}

</script>
<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: black;
  color:white;
}
.container {
  max-width: 100%;
  max-height: 100%;
  margin: 30px auto;
  overflow: auto;
  padding: 30px;
  border-radius: 5px;
  /*background-image: url("https://media.istockphoto.com/photos/defocused-particles-background-picture-id1151621425?b=1&k=20&m=1151621425&s=170667a&w=0&h=cB0k4z9NvMjor1ERZE69zK6G6X6ZMlZ2TlY0poHx7SE=");*/
  /*background-image: url("https://images.cdn2.stockunlimited.net/preview1300/music-event-background-concept_1934780.jpg"); */
  background-image: url("https://t3.ftcdn.net/jpg/04/49/47/16/360_F_449471656_6tH7Glz5CtouQAPNM9188r4ozu0hlv0t.jpg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}

div{
  margin-bottom: 0.5em;
}
.About{
  width: 12%;
  float: right;
  padding-right: 6%;
  
}
a{
    text-decoration: none;
    color: rgb(2, 7, 16);

}
button{
    float: center;
    font-size:30px;
    font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: rgb(13, 115, 136);
    width:100%;
    border:3px solid rgb(46, 99, 173);
}
</style>


