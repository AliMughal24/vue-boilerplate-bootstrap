<template>
  <div>
    <p>Score</p>
    <b-form-rating
      id="rating-inline reviews"
      :value="review"
      inline
    ></b-form-rating>
  </div>
</template>
<script>
export default {
  name: "Reviews",
  data() {
    return {};
  },
  props: ["review"],
};
</script>

<style scoped>
.form-control {
  margin-top: 35px;
  border: none !important;
}
.form-control:focus {
  box-shadow: none !important;
}
</style>
