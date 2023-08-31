<template>
  <div>
    <div>
      <div class="d-flex align-items-end">
        <multiselect
          class="multiSelector"
          v-model="value"
          :options="options"
          :searchable="false"
          :close-on-select="false"
          :show-labels="false"
          placeholder="Pick a name"
        ></multiselect>
        <svg
          @click="addUser"
          class="px-2"
          xmlns="http://www.w3.org/2000/svg"
          height="1em"
          viewBox="0 0 448 512"
        >
          <!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
          <path
            d="M256 80c0-17.7-14.3-32-32-32s-32 14.3-32 32V224H48c-17.7 0-32 14.3-32 32s14.3 32 32 32H192V432c0 17.7 14.3 32 32 32s32-14.3 32-32V288H400c17.7 0 32-14.3 32-32s-14.3-32-32-32H256V80z"
          />
        </svg>
        <svg
          @click="removeUser()"
          class="pl-1"
          xmlns="http://www.w3.org/2000/svg"
          height="1em"
          viewBox="0 0 448 512"
        >
          <!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
          <path
            d="M432 256c0 17.7-14.3 32-32 32L48 288c-17.7 0-32-14.3-32-32s14.3-32 32-32l352 0c17.7 0 32 14.3 32 32z"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
import Multiselect from "vue-multiselect";

export default {
  name: "MultiSelector",
  components: {
    Multiselect,
  },
  data() {
    return {
      value: "",
      options: [
        "Sarah Johnson",
        "Michael Smith",
        "Emily Davis",
        "Christopher Brown",
        "Jessica Wilson",
      ],
    };
  },
  methods: {
    addUser() {
      this.$emit("add-show");
    },
    removeUser() {
      this.$emit("removeShow");
    },
  },
};
</script>

<style scoped>
.multiSelector {
  border-bottom: 2px solid #aeaeae;
}
</style>
