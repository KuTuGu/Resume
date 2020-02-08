<template>
  <div id="app">
    <div class="mainContent">
      <PersonalInfo :Info="Info.PersonalInfo" />
      <!-- <ProjectExperience :Info="Info.ProjectExperience" /> -->
      <div class="projectExperience">项目经历</div>
      <div v-for="i of Info.ProjectExperience" :key="i">
        <InfoItem :Info="i" :whiteTitle="true" />
      </div>
    </div>
    <div class="sideBar">
      <div v-for="i of Info.sideBar" :key="i">
        <InfoItem :Info="i" :smallTitle="true"/>
      </div>
    </div>
  </div>
</template>

<script>
import InfoItem from './components/infoItem.vue'
import PersonalInfo from './components/personalInfo.vue'
import Info from "./info.json"

export default {
  name: 'App',
  components: {
    InfoItem,
    PersonalInfo
  },
  data: () => ({
    Info,
  }),
} 
</script>

<style>
html, body{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: #D9D9D9;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: space-around;
  width: 80%;
  background-color: white;
  color: #2c3e50;
  padding: 40px 15px;
  margin: 20px auto;
  overflow: hidden;
  box-sizing: border-box;
}
p {
  margin: 10px 0;
}
.mainContent, .sideBar{
  display: inline-block;
  width: 60%;
}
.sideBar{
  width: 30%;
  padding: 25px;
  border-left: solid 1px black; 
  display: inline-flex;
  flex-wrap: wrap;
  align-content: space-around;
}
.projectExperience{
  margin: 20px 0;
  font-size: 20px;
  width: 30%;
  text-align: center;
  background-color: #333333;
  color: white;
  padding: 5px;
  border: solid 1px black;
}
</style>
