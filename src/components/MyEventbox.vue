<template>
     <div class="MyEventbox">
        <div v-for="events in events" :key="events.id" >         
                <MyEvents :events="events"/>
        </div>   
     </div>
</template>

<script>

import MyEvents from "./MyEvents.vue"
export default{
    name: 'MyEventbox',
    components: {
        MyEvents
    },
    props: {
        events: Array
    }
}
</script>

<style>

.MyEventbox{

    width : 90%;
    height: 90%;
    background-color: black;
    padding: 1em;
    color: gray;
    display: grid;
    grid-template-columns: repeat(2, minmax(300px, 1.5fr));
    grid-gap: 30px;
    align-items: stretch;
    font-size: 2vmin;
    margin: 5% 5% 5% 5%;
    background-image: url("https://t3.ftcdn.net/jpg/04/49/47/16/360_F_449471656_6tH7Glz5CtouQAPNM9188r4ozu0hlv0t.jpg");
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    
}
</style>