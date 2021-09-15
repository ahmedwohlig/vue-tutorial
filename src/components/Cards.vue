<template >
  <div class="card">
    <h5>{{ name }}</h5>
    <p>{{ details }}</p>
    <h6>{{ footer }}</h6>
  </div>
</template>
<script>
export default {
  props: ["name", "details", "footer"],
};
</script>
<style scoped>
.card {
  display: flex;
  flex-direction: column;
  width: 120px;
  background-color: rgba(209, 209, 156, 0.726);
  align-items: center;
  margin: auto;
}
</style>