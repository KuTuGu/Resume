<template>
    <div class="personalInfo">
        <div class="signature">{{Info.signature}}</div>
        <p class="name">{{Info.name}}</p>
        <p class="job">{{Info.job}}</p>
        <div class="intro" v-for="i of Info.intro" :key="i">{{i}}</div>
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
.intro {
    font-size: 14px;
    line-height: 1;
    padding-bottom: 10px;
}
.intro:last-child {
    padding-bottom: 0px;
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
    margin: 10px 0;
}
.job{
    font-size: 18px;
    margin: 10px 0;
}
</style>
