<template>
  <div>
    <Modal :property="property" :clickNum="clickNum" :modalOpen="modalOpen" />
    <div class="menu">
      <!-- 자료안의 데이터 갯수만큼 반복됨 -->
      <!-- 그럼 작명한 변수는 데이터안의 자료가 됨 -->
      <a v-for="menu in menus" :key="menu">{{ menu }}</a>
    </div>
    <Discount />

    <div id="app">
      <!-- <div>
        <img :src="property[0].image" class="roomImg" />
        <h4 class="logo" :style="스타일" @click="modalOpen = true">
          {{ property[0].title }}
        </h4>
        <p>{{ property[0].price }}</p>
        v-on:click을 @로 대체 가능
        <button @click="신고수1++">허위매물 신고</button>
        <button @click="신고수[0]++">허위매물 신고</button>
        <span>신고수 : {{ 신고수[0] }}</span>
      </div> -->

      <!-- <div v-for="product in products" :key="product">
        <h4 class="logo">
          {{ product }}
          <p>50만원</p>
        </h4>
      </div> -->

      <Card :property="property[i]" v-for="(room, i) in property" :key="i" />
    </div>
  </div>
</template>

<script>
import property from "./propertyDate.js";
import Discount from "./components/Discount.vue";
import Modal from "./components/Modal.vue";
import Card from "./components/Card.vue";

export default {
  name: "App",
  data() {
    //데이터 보관함
    return {
      스타일: "color: blue",
      menus: ["Home", "Shop", "About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      property: property,
      신고수: [0, 0, 0],
      modalOpen: false,
      clickNum: 0,
    };
  },
  // 함수 만드는 공간 정해져 있음 : data끝나는 부분
  // 함수 안에서 데이터 쓸 때 this.데이터명
  methods: {},

  components: {
    Discount: Discount,
    Modal,
    Card,
  },
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

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
