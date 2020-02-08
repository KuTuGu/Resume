<template>
  <div :class="smallTitle ? 'leftMove' : ''">
    <div v-if="smallTitle" class="title smallTitle" :class="whiteTitle ? 'title-white' : ''">{{Info.title}}</div>
    <p v-else class="title" :class="whiteTitle ? 'title-white' : ''">{{Info.title}}</p>
    <ul>
      <li v-for="i of Info.msg" :key="i">{{i}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'InfoItem',
  props: {
    Info: {
      title: String,
      msg: Array,
    },
    whiteTitle: Boolean,
    smallTitle: Boolean,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title{
  text-align: center;
  background-color: #333333;
  color: white;
  padding: 5px;
  border: solid 1px black;
}
.title-white{
  background-color: white;
  color: black;
  font-weight: bold;
  text-align: left;
  padding-left: 15px; 
}
.smallTitle{
  display: inline-block;
  padding: 5px 25px;
  margin-left: 20px; 
}
ul{
  padding-right: 20px;
}
li{
  word-break:break-all;
}
.leftMove{
  margin-left: -25px;
}
</style>