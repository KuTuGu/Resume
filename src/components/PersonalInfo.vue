<template>
  <div class="personalInfo">
    <div class="signature">{{info.signature}}</div>
    <p class="name">{{info.name}}</p>
    <p class="job">{{info.job}}</p>
    <div class="intro" v-for="(i, key) of info.intro" :key="key">{{i}}</div>
  </div>
</template>

<script setup lang="ts">
  defineProps<{
    info: {
      name: string;
      job: string;
      intro: Array<string>;
      signature: string;
    }
  }>()
</script>

<style>
.personalInfo {
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
.signature {
  font-weight: bold;
  border: solid 1px black;
  padding: 2px 10px;
  margin-left: -10px;
}
.name {
  font-weight: bold;
  font-size: 30px;
  margin: 10px 0;
}
.job {
  font-size: 18px;
  margin: 10px 0;
}
</style>
