<template>
  <div>
    <!-- <p class="text-left text-dark mb-3" v-if="$route.path !== '/Component'">
      {{ header }}
    </p>
    <h4 class="text-left text-color mb-4" v-else>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="25"
        height="25"
        fill="currentColor"
        class="bi bi-chat-fill text-color mx-1"
        viewBox="0 0 16 16"
      >
        <path
          d="M8 15c4.418 0 8-3.134 8-7s-3.582-7-8-7-8 3.134-8 7c0 1.76.743 3.37 1.97 4.6-.097 1.016-.417 2.13-.771 2.966-.079.186.074.394.273.362 2.256-.37 3.597-.938 4.18-1.234A9.06 9.06 0 0 0 8 15z"
        /></svg
      >Account Comments
    </h4>
    <div class="account-scrollbar">
      <div class="d-flex px-2">
        <div class="d-flex">
          <svg
            v-b-modal.modal-sm
            xmlns="http://www.w3.org/2000/svg"
            width="25"
            height="25"
            fill="currentColor"
            class="bi bi-plus-square add-icon text-color"
            viewBox="0 0 16 16"
          >
            <path
              d="M14 1a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1h12zM2 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H2z"
            />
            <path
              d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"
            />
          </svg>
          <label v-b-modal.modal-sm class="text-color px-2"
            >Add new comment</label
          >
        </div>
        <button class="btn btn-sm btn-primary mx-4 mx-md-5 mb-3">Save</button>
      </div>
    </div> -->

    <div class="bg-light">
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
      <div class="text-left mx-1 py-1">
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
