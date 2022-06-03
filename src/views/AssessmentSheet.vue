<template>
  <div>
    <div class="mt-3">
      <div class="grey d-flex lighten-3">
        <p class="align-center font-weight-bold mt-3 mx-5">
          Claim Number - 4340002739
        </p>
        <v-divider vertical class="my-2"></v-divider>
        <p class="red--text font-weight-bold darken-3 mt-3 mx-5">
          FEATURE CLAIM
        </p>
        <v-spacer></v-spacer>
        <p class="blue--text text-caption mt-3 mr-5">View Details</p>
      </div>

     
      <div class="mt-6">
        <v-btn to="/"
          class=" pa-4 ml-0 text-subtitle-2 "
          style="text-transform: none; "
        >
          Claim Details</v-btn
        >
        <v-btn
          outlined
          class="assbtn ml-1 white--text"
          elevation="0"
         
          style="text-transform: none; background: #1ebbd9"
          >Assessment Sheet</v-btn
        >
        <v-divider class="mr-16"></v-divider>
      </div>
    </div>
    <div class="mt-16">
      <v-img
        src="../assets/Screenshot 2022-05-30 184620.jpg"
        height="200"
        width="300"
        class="mx-auto"
      />

      <v-btn to="/AddAssessmentSheet" id="img" class="light-blue white--text text-caption"
        ><v-icon>mdi-plus-box-outline</v-icon>
        <v-divider vertical class="mx-3 grey lighten-5"></v-divider>
        Add Assessment</v-btn
      >
    </div>
  </div>
</template>

<script>
import "../assets/Main.css";
export default {
  name: "AssessmentSheet",
};
</script>

<style scoped>
#img {
  margin: 0 550px;
}
</style>
