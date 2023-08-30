<template>
  <div>
    <div class="bg-light py-2">
      <div class="d-flex align-items-center">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-trash-fill text-color mx-1"
          viewBox="0 0 16 16"
        >
          <path
            d="M2.5 1a1 1 0 0 0-1 1v1a1 1 0 0 0 1 1H3v9a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V4h.5a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1H10a1 1 0 0 0-1-1H7a1 1 0 0 0-1 1H2.5zm3 4a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7a.5.5 0 0 1 .5-.5zM8 5a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7A.5.5 0 0 1 8 5zm3 .5v7a.5.5 0 0 1-1 0v-7a.5.5 0 0 1 1 0z"
          />
        </svg>

        <span class="text-color"
          ><b-avatar size="sm" class="mx-1"></b-avatar>{{ name }}</span
        >
        <span class="text-color px-3 px-md-5">{{ date }}</span>
      </div>
      <div class="text-left mx-1 py-2">
        <span>{{ description }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Comments",
  props: ["name", "date", "description"],
};
</script>

<style scoped>
.add-icon:focus {
  outline: none !important;
}
.form-control:focus {
  box-shadow: none !important;
}
</style>
