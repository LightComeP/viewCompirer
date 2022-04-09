<template>
<div class="menu">
  <a v-for="(value,key) in menus" :key="key"  href="">{{value}}</a>
</div>

  <div class="black-bg" v-if="modaltoogle" @click="modaltoogle = !modaltoogle">
    <div class="white-bg">
      <h4>상세 페이지</h4>
      <p>내용스</p>
    </div>
  </div>





  <div v-for="(value, key) in dbData" :key="key">
    <img :src="value.image" alt="" style="width: 40%" @click="modaltoogle = !modaltoogle">
    <h4>{{value.title}}</h4>
    <p>{{value.price}} 원</p>
  </div>

</template>

<script>
// import * as jsonData from './dataJS/example.json';
// jsonData;

import {dbData}   from "./dataJS/data";
dbData;
export default {
  name: 'App',
  data(){
    return {
      menus : [
        "HOME",
        "About",
      ],
      modaltoogle: false,
      dbData: dbData

    }
  },
  methods: {
    increase(key){
      console.log(this.dumiData);
      this.reportCount[key]++;
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu{
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color : white;
  padding : 10px;
}

body{
  margin: 0;
}

div {
  box-sizing: border-box;
}
.black-bg {
  width : 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
