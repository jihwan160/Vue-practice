<template>


  <div class="black-bg" v-if="modalopen == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지임</p>
      <button @click="modalopen = false">닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="(a,i) in menus" :key="i">{{a}}</a>
  </div>






  <div v-for="(k,index) in products" :key="index">
    <img src="./assets/room0.jpg" alt="" class="room-img">
    <h4 @click="modalopen = true">{{products[index]}}</h4>
    <p>{{price[index]}} 만원</p>
    <button @click="num[index] += 1">허위매물신고</button> <span>신고 수 : {{num[index]}}</span>
  </div>


</template>

<script>


export default {
  name: 'App',

  data(){
    return{
      modalopen : false,
      price : [60,70,80],
      products : ['역삼동원룸', '천호동원룸' , '마포구원룸'],
      menus : ['Home', 'Shop', 'About'],
      num : [0,0,0]
    }
  },


  components: {
    
  }
  
}
</script>

<style>

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}




.room-img {
  width: 100%;
  margin-top: 40px;
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
</style>
