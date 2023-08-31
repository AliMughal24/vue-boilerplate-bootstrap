<template>
  <div>
    <b-container>
      <div class="d-flex">
        <b-button @click="onBackClick" class="my-3" variant="outline-primary"
          >Back</b-button
        >
      </div>
      <b-row class="justify-content-center">
        <b-col sm="8" md="6" lg="5">
          <p class="text-dark mb-0">Rating</p>
          <div>
            <b-form-rating
              v-model="selectedRating"
              @change="filterReviews"
              id="rating-inline reviews"
              inline
            ></b-form-rating>
            <div v-for="review in filteredReviews" :key="review.id">
              <p class="text-dark">{{ review.text }}</p>
            </div>
          </div>
          <hr />
          <h4
            class="text-left text-dark mb-4"
            v-if="$route.path !== '/Comment'"
          >
            Comments
          </h4>
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
          <div class="account-scrollbar bg-light">
            <div class="d-flex px-2 py-2">
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
              <button class="btn btn-sm btn-primary mx-4 mx-md-5 mb-3">
                Save
              </button>
              <b-modal id="modal-sm" size="sm" title="Rating feedback">
                <div class="">
                  <label for="rating-inline">Reviews:</label>
                  <b-form-rating
                    class=""
                    id="rating-inline reviews"
                    inline
                  ></b-form-rating>
                </div>
                <b-form-textarea
                  class="text-dark mt-2 border"
                  id="textarea-no-resize"
                  placeholder="textarea"
                  rows="3"
                  no-resize
                ></b-form-textarea>
              </b-modal>
            </div>
            <Comments
              class="my-3"
              v-for="(comment, index) in comments"
              :key="index"
              :name="comment.name"
              :description="comment.description"
              :date="comment.date"
            />
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Comments from "../components/Comments.vue";

export default {
  name: "Comment",
  components: {
    Comments,
  },
  data() {
    return {
      reviews: [
        { id: 1, rating: 1, text: "Risk factor:high" },
        { id: 2, rating: 2, text: "Risk factor:high" },
        { id: 2, rating: 3, text: "Risk factor:medium" },
        { id: 2, rating: 4, text: "Risk factor:medium" },
        { id: 2, rating: 5, text: "Risk factor:low" },
      ],
      selectedRating: "",
      filteredReviews: [],
      comments: [
        {
          name: "alee",
          description: "Reached out to bob today about this thing",
          date: "28/08/2023 6:12pm",
        },
        {
          name: "alee",
          description:
            "Reached out to bob today about this thing Reached out to bob today about this thing Reached out to bob today about this thing ",
          date: "28/08/2023 6:12pm",
        },
        {
          name: "alee",
          description: "Reached out to bob today about this thing",
          date: "28/08/2023 6:12pm",
        },
        {
          name: "alee",
          description: "Reached out to bob today about this thing",
          image: "",
          date: "28/08/2023 6:12pm",
        },
        {
          name: "alee",
          description:
            "Reached out to bob today about this thing Reached out to bob today about this thing",
          image: "",
          date: "28/08/2023 6:12pm",
        },
        {
          name: "alee",
          description:
            "Reached out to bob today about this thing Reached out to bob today about this thing Reached out to bob today about this thing",
          image: "",
          date: "28/08/2023 6:12pm",
        },
      ],
    };
  },
  methods: {
    filterReviews() {
      this.filteredReviews = this.reviews.filter(
        (review) => review.rating === this.selectedRating
      );
    },
    onBackClick() {
      this.$router.push("/");
    },
  },
};
</script>

<style scoped>
.add-icon:focus {
  outline: none !important;
}
.account-scrollbar {
  height: 600px !important;
  overflow: auto !important;
}
::-webkit-scrollbar {
  width: 10px !important;
}

::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 10px !important;
}
::-webkit-scrollbar-thumb {
  background: #6697e0 !important;
  border-radius: 10px !important;
}
</style>
