<template>
  <div class="blackBg" v-if="modalOpen == true">
    <div class="whiteBg">
      <!-- props는 read-only임 재할당하면 안됨 예를 들어 modalOpen = false 같이 -->
      <button @click="$emit('openModal')">닫기</button>
      <img :src="property[clickNum].image" class="modalImg" />
      <h4>{{ property[clickNum].title }}</h4>
      <p>{{ property[clickNum].content }}</p>
      <!-- <input @input="month = $event.target.value" /> -->
      <input v-model.number="month" />
      <p>
        {{ month }} 개월 선택한 금액 = {{ property[clickNum].price * month }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MODAL",
  props: {
    // props이름: 자료형
    property: Array,
    clickNum: Number,
    modalOpen: Boolean,
  },
  data() {
    return {
      month: 1,
    };
  },
};
</script>

<style>
.blackBg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.whiteBg {
  width: 100%;
  background-color: white;
  padding: 20px;
}
.modalImg {
  width: 100%;
}
</style>
