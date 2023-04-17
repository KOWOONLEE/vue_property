<template>
  <div class="discount">
    <h4>지금 결제하면 {{ time }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: "DISCOUNT",
  data() {
    return { time: 30 };
  },
  mounted() {
    setInterval(() => {
      this.time--;
    }, 1000);
  },
};
</script>

<style>
.discount {
  background-color: lightgrey;
  padding: 20px;
  margin: 10px;
  border-radius: 5px;
}
</style>
