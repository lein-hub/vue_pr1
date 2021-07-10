<template>
  <div class="black-bg" v-if="isOpen">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="isOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="i in menus" :key="i" href="">{{ i }}</a>
  </div>

  <div>
    <div v-for="(a,i) in oneRooms" :key="i">
      <img src="./assets/room0.jpg" alt="" class="room-class">
      <h4 @click="isOpen = !isOpen">{{ a.title }}</h4>
      <p>{{ a.price }} 원</p>
    </div>
  </div>
</template>

<script>

import data from './assets/oneRooms';

export default {
  name: 'App',
  data(){
    return {
      oneRooms : data,
      isOpen : false,
      prices : [50, 30, 70],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus : ['Home', 'Products', 'About'],
      num : [0,0,0],
    }
  },
  components: {
  }
}
</script>

<style>
body {
  margin : 0
}
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-class {
  width: 400px;
}
</style>
