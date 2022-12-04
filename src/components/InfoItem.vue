<template>
  <div :class="smallTitle ? 'leftMove' : ''">
    <div v-if="smallTitle" class="title smallTitle" :class="whiteTitle ? 'title-white' : ''">{{info.title}}</div>
    <p v-else class="title" :class="whiteTitle ? 'title-white' : ''">{{info.title}}</p>
    <ul v-if="Array.isArray(info.msg)">
      <li v-for="(i, key) of info.msg" :key="key">{{i}}</li>
    </ul>
    <ul v-else>
      <li v-for="(i, key) of Object.keys(info.msg)" :key="key">
        <a :href="info.msg[i]" target="_blank">{{i}}</a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
  defineProps<{
    info: {
      title: string;
      msg: Array<string> | Record<string, string>;
    },
    whiteTitle?: boolean;
    smallTitle?: boolean;
  }>()
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title {
  text-align: center;
  background-color: #333333;
  color: white;
  padding: 2px 5px;
  border: solid 1px black;
}
.title-white {
  background-color: white;
  color: black;
  font-weight: bold;
  text-align: left;
  padding-left: 15px; 
}
.smallTitle {
  display: inline-block;
  padding: 2px 25px;
  margin-left: 20px; 
}
ul {
  padding-right: 10px;
  padding-inline-start: 2em;
}
li {
  word-break:break-all;
  font-size: 14px;
  margin: 5px 0;
}
.leftMove {
  margin-left: -25px;
}
a {
  text-decoration: none;
}
</style>