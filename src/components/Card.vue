<template>
  <div>
    <img :src="property.image" class="roomImg" />
    <h4 @click="$emit('openModal', property.id)">
      {{ property.title }}
    </h4>
    <p>{{ property.price }}</p>
  </div>
</template>

<script>
export default {
  name: "CARD",
  props: { property: Object },
};
</script>

<style>
.roomImg {
  width: 100%;
  margin-top: 40px;
}
</style>
