<template>
    <div class="personalInfo">
        <div class="signature">{{Info.signature}}</div>
        <p class="name">{{Info.name}}</p>
        <p class="job">{{Info.job}}</p>
        <div v-for="i of Info.intro" :key="i">{{i}}</div>
    </div>
</template>

<script>
export default {
    name: 'PersonalInfo',
    props: {
        Info: {
            name: String,
            job: String,
            intro: String,
            signature: String,
        }
    }
} 
</script>

<style>
.personalInfo{
    padding: 0 10% 20px 10px;
    border-bottom: solid 1px black;
}
.signature{
    font-weight: bold;
    border: solid 1px black;
    padding: 2px 10px;
    margin-left: -10px;
}
.name{
    font-weight: bold;
    font-size: 30px;
    margin: 15px 0;
}
.job{
    font-size: 20px;
    margin: 15px 0;
}
</style>
