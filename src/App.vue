<template>
  <div id="app">
    <div class="sideBar">
      <div v-for="i of Info.sideBar" :key="i">
        <InfoItem :Info="i" :smallTitle="true"/>
      </div>
    </div>
    <div class="mainContent">
      <PersonalInfo :Info="Info.PersonalInfo" />
      <!-- <ProjectExperience :Info="Info.ProjectExperience" /> -->
      <div class="projectExperience">项目经历</div>
      <div v-for="i of Info.ProjectExperience" :key="i">
        <InfoItem :Info="i" :whiteTitle="true" />
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
  justify-content: space-between;
  width: 794px;
  /* height: 1123px; */
  background-color: white;
  color: #2c3e50;
  padding: 20px 15px;
  margin: 20px auto;
  overflow: hidden;
  box-sizing: border-box;
}
p {
  margin: 10px 0;
}
.mainContent, .sideBar{
  display: inline-block;
  width: 72%;
}
.sideBar{
  width: 24%;
  margin-left: 8px;
  padding: 25px 8px 25px 0;
  border-right: solid 1px black; 
  display: inline-flex;
  flex-wrap: wrap;
  align-content: space-around;
}
.projectExperience{
  margin: 15px 0;
  font-size: 20px;
  width: 30%;
  text-align: center;
  background-color: #333333;
  color: white;
  padding: 2px 5px;
  border: solid 1px black;
}
</style>
