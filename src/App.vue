<template>
  <div>
    <div class="menu">
      <!-- 자료안의 데이터 갯수만큼 반복됨 -->
      <!-- 그럼 작명한 변수는 데이터안의 자료가 됨 -->
      <a v-for="menu in menus" :key="menu">{{ menu }}</a>
    </div>
    <div id="app">
      <div>
        <h4 class="logo" :style="스타일">{{ products[0] }}</h4>
        <p>70 만원</p>
        <!-- v-on:click을 @로 대체 가능 -->
        <!-- <button @click="신고수1++">허위매물 신고</button> -->
        <button @click="신고수[0]++">허위매물 신고</button>
        <span>신고수 : {{ 신고수[0] }}</span>
      </div>
      <div>
        <h4>{{ products[1] }}</h4>
        <p>50 만원</p>
        <button @click="신고수[1]++">허위매물 신고</button>
        <span>신고수 : {{ 신고수[1] }}</span>
      </div>
      <div>
        <h4>{{ products[2] }}</h4>
        <p>60 만원</p>
        <button @click="신고수[2]++">허위매물 신고</button>
        <span>신고수 : {{ 신고수[2] }}</span>
      </div>
      <!-- <div v-for="product in products" :key="product">
        <h4 class="logo">
          {{ product }}
          <p>50만원</p>
        </h4>
      </div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    //데이터 보관함
    return {
      스타일: "color: blue",
      menus: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      신고수: [0, 0, 0],
      신고수1: 0,
      신고수2: 0,
      신고수3: 0,
    };
  },
  // 함수 만드는 공간 정해져 있음 : data끝나는 부분
  // 함수 안에서 데이터 쓸 때 this.데이터명
  methods: {},

  components: {},
};
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
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
