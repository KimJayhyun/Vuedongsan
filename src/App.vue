<template>
  <div class="menu">
      <a v-for="(a, i) in menus" :key="i" > {{ a }} </a>
      
  </div>
  
  
  <div>
    <h4 class="red" :style="스타일"> {{ products[0] }} </h4>
    <p> {{ price1 }} 만원 </p>
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
      
      // html attribute는 : 로 적용 가능
      스타일 : "color : blue",

      menus : ['Home', "Products", 'About'],
      products : ['일원동', '이원동', '삼원동']
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
