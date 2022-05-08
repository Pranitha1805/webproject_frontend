<template>
<div>
    <h2><b> {{EventName}}</b></h2>
    <h2><b> {{UniversityName}}</b></h2>
</div>
</template>
<script>
export default{
    name: 'MyHeader',
    props:{
        EventName: String,
        UniversityName:String
    }
}
</script>
<style scoped>
div{
    text-align: center;
    padding: 0% 20%;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}
</style>