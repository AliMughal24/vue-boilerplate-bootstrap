<template>
  <div>
    <h4>Score</h4>

    <b-form-rating id="rating-inline reviews" inline></b-form-rating>
  </div>
</template>
<script>
export default {
  name: "Reviews",
  data() {
    return {};
  },
};
</script>

<style scoped>
.form-control {
  margin-top: 65px;
  border: none !important;
}
.form-control:focus {
  box-shadow: none !important;
}
</style>
