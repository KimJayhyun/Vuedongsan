<template>


  <div class="black-bg">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>






  <div class="menu">
      <a v-for="(a, i) in menus" :key="i" > {{ a }} </a>
      
  </div>
  
  <div v-for="(a, i) in products" :key="i">
    <h4 class="red" :style="스타일"> {{ a }} </h4>
    <p> {{ prices[i] }} 만원 </p>  
    
    <button @click="increase(i)">허위매물신고</button><span>신고수 : {{ votes[i] }}</span>
  </div> 

  <hr>

  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 class="red" :style="스타일"> {{ products[0] }} </h4>
    <p> {{ price1 }} 만원 </p>
    <!-- <button v-on:click="console.log('hi')">허위매물신고</button><span>신고수 : 0</span> -->
    <!-- <button @click="신고수++">허위매물신고</button><span>신고수 : {{ 신고수 }}</span> -->
    
    <button @click="increase">허위매물신고</button><span>신고수 : {{ 신고수 }}</span>
  </div>

  <div>   
    <h4> {{ products[1] }} </h4>
    <p> {{ price2 }} 만원 </p>
  </div>

</template>

<script>

export default {
  name: 'App',
  // 데이터 바인딩을 하면 실시간 렌더링 가능
  data() {
    return {
      price1 : 60,
      price2 : 70,
      신고수 : 0,
      // html attribute는 : 로 적용 가능
      스타일 : "color : blue",

      menus : ['Home', "Products", 'About'],
      
      products : ['일원동', '이원동', '삼원동'],
      prices : [1, 2, 3],
      votes : [0, 0, 0]
    }
  },

  methods: {
    increase(i) {
      this.votes[i] ++;
    }  
  },

  components: {
    
  }
}
</script>

<style>
.romm-img {
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
