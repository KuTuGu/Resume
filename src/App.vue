<template>
  <div id="resume">
    <div class="sideBar">
      <div v-for="(i, key) of info.SideBar" :key="key">
        <InfoItem :info="i" :smallTitle="true"/>
      </div>
    </div>
    <div class="mainContent">
      <PersonalInfo :info="info.PersonalInfo" />
      <div class="projectExperience">项目经历</div>
      <div v-for="(i, key) of info.ProjectExperience" :key="key">
        <InfoItem :info="i" :whiteTitle="true" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import InfoItem from './components/InfoItem.vue'
import PersonalInfo from './components/PersonalInfo.vue'
import Info from "./info.json"

const info = ref(Info);
</script>

<style>
#resume {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: space-between;
  width: 794px;
  height: 1123px;
  background-color: white;
  color: #2c3e50;
  padding: 20px 15px;
  margin: 20px auto;
  overflow: hidden;
  box-sizing: border-box;
}

.mainContent, .sideBar {
  display: inline-block;
  width: 72%;
}

.sideBar {
  width: 24%;
  margin-left: 8px;
  padding: 0 8px 25px 0;
  border-right: solid 1px black; 
  display: inline-flex;
  flex-wrap: wrap;
}

.projectExperience {
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
