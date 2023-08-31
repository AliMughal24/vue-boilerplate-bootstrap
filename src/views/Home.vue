<template>
  <b-container>
    <div class="d-flex">
      <b-button variant="outline-primary" class="my-3" @click="NextPage"
        >NextPage</b-button
      >
    </div>
    <div v-for="(project, index) in projects" :key="index">
      <h4 class="text-dark text-left mt-3">{{ project.role }}</h4>
      <b-row class="my-4">
        <b-col sm="8" md="6" lg="5">
          <p class="typo__label text-dark text-left">Name</p>

          <div
            v-for="(user, userIndex) in project.users"
            :key="userIndex"
            class="user-list"
          >
            <MultiSelector
              @add-show="addUser(index)"
              @removeShow="removeUser(index, userIndex)"
              class="mt-3"
            /></div
        ></b-col>
        <b-col sm="8" md="6" lg="2">
          <p class="mb-">Score</p>

          <div
            v-for="(user, userIndex) in project.users"
            :key="userIndex"
            class="user-list"
          >
            <Reviews :review="user.review" class="mt-4 mt-md-0" /></div></b-col
        ><b-col sm="8" md="6" lg="5">
          <p class="text-left text-dark" v-if="$route.path !== '/Comment'">
            Comments
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

          <div
            v-for="(user, userIndex) in project.users"
            :key="userIndex"
            class="user-list"
          >
            <div class="d-flex">
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
            </div>
            <Comments
              class="mt-3 mt-md-3 mt-lg-0"
              v-for="(comment, index) in user.comments"
              :key="index"
              :name="comment.name"
              :description="comment.description"
              :date="comment.date"
            /></div
        ></b-col>
      </b-row>
      <!-- </div> -->
    </div>

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
      ></b-form-textarea> </b-modal
  ></b-container>
</template>

<script>
// @ is an alias to /src
import MultiSelector from "@/components/MultiSelector.vue";
import Reviews from "@/components/Reviews.vue";
import Comments from "@/components/Comments.vue";

export default {
  name: "Home",
  components: {
    MultiSelector,
    Reviews,
    Comments,
  },
  data() {
    return {
      projects: [
        {
          role: "Owner/Client",
          users: [
            {
              review: "",
              comments: [
                {
                  name: "alee",
                  description: "Reached out to bob today about this thing",
                  date: "28/08/2023 6:12pm",
                },
              ],
            },
          ],
        },
        {
          role: "Designers/Consultants",
          users: [
            {
              review: "",
              comments: [
                {
                  name: "alee",
                  description: "Reached out to bob today about this thing",
                  date: "28/08/2023 6:12pm",
                },
              ],
            },
          ],
        },
        {
          role: "GC",
          users: [
            {
              review: "",
              comments: [
                {
                  name: "alee",
                  description: "Reached out to bob today about this thing",
                  date: "28/08/2023 6:12pm",
                },
              ],
            },
          ],
        },
        {
          role: "Trades",
          users: [
            {
              review: "",
              comments: [
                {
                  name: "alee",
                  description: "Reached out to bob today about this thing",
                  date: "28/08/2023 6:12pm",
                },
              ],
            },
          ],
        },
        {
          role: "Vendors",
          users: [
            {
              review: "",
              comments: [
                {
                  name: "alee",
                  description: "Reached out to bob today about this thing",
                  date: "28/08/2023 6:12pm",
                },
              ],
            },
          ],
        },
      ],
    };
  },
  methods: {
    NextPage() {
      this.$router.push("/Comment");
    },
    addUser(projectIndex) {
      this.projects[projectIndex].users.push({
        review: "",
        comments: [
          {
            name: "alee",
            description: "Reached out to bob today about this thing",
            date: "28/08/2023 6:12pm",
          },
        ],
      });
    },
    removeUser(projectIndex, userIndex) {
      this.projects[projectIndex].users.splice(userIndex, 1);
    },
  },
};
</script>
<style scoped>
.add-icon:focus {
  outline: none !important;
}
.user-list {
  height: 110px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 20px 0;
}
</style>
