<template>
    <div >
        <ul><h4>Guest Lecturer {{events.id}}</h4></ul>
        <ul><h4>Lecture given by - {{events.name}}</h4></ul>
        <ul><h4>Event is on {{getDate(events.date)}}</h4></ul>
        <article class="data">
            <ul>Begins at: {{events.timing[0]}}</ul>
            <ul>Ends at: {{events.timing[1]}}</ul>
            <ul>Venue - {{events.venue}}</ul>
            <p :class="events.availabilty ? 'green': 'red' ">Availability</p>
        </article>    
    </div>
</template>
<script>

export default{
    name: 'MyEvents',
    props:{
        events: Array,
    },   
    methods: {
        getDate(datetime) {
            let date = new Date(datetime);
            let dateString = `${date.getFullYear()}-${date.getDate()}-${date.getMonth() + 1}`
            return dateString
        }
    }
}

</script>
<style scoped>

template{
    margin-left: 10%;
    margin-right: 10%;
    margin-top: 10%;
    margin-bottom: 10%;
}


p{
    margin: 2px;
    float: center;
}

.data{
    margin-bottom: 0px;
    bottom: 0;
    float: right;
}

h4{
    margin: 2px;
}

h3{
    margin: 2px;
    float: right;
    bottom: 0px;
}


div{
    width: 90%;
    height: 90%;
    color: rgb(30, 238, 148);
    padding: 1em;
    border-radius: 5px;
    border: 0.3em solid  white;
    margin-bottom: 25px auto;
    overflow: auto;
    
  }
div:hover {
 border: 0.3em solid red;
 color: white;
}


.red{
background-color: rgb(246, 42, 0) !important;

}
.green{
background-color: rgb(115, 159, 61) ;
}
.eventbg{
    width: 1%;
    float: right ;
    position: inherit; top: 0px;
}

</style>