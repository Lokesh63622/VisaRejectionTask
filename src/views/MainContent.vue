<template>
  <div>
    <div class="mt-3">
      <div class="grey d-flex lighten-3">
        <p class="align-center font-weight-bold mt-3 mx-5">
          Claim Number - 4340002739
        </p>
        <v-divider vertical class="my-2"></v-divider>
        <b class="red--text font-weight-bold darken-3 mt-3 mx-5">NEW CLAIM</b>
        <v-spacer></v-spacer>
        <p class="blue--text mt-3 mr-5">View Details</p>
      </div>

      <div class="mt-6">
        <v-btn
          class="white--text pa-4 ml-0 text-subtitle-2"
          style="text-transform: none; background: #1ebbd9"
        >
          Claim Details</v-btn
        >
        <v-btn
          outlined
          class="assbtn ml-1"
          elevation="0"
          to="/AssessmentSheet"
          style="text-transform: none"
          >Assessment Sheet</v-btn
        >
        <v-divider class="mr-16"></v-divider>
      </div>
      <div class="font-weight-bold ma-4 headColour--text headColour">
        Visa Rejection Claim
      </div>
    </div>
    <!-- -------------------BASIC DETAILS-------------------------------- -->
    <template>
      <div>
        <div>
          <!-- basic details -->
          <div style="border: 1px solid grey">
            <div style="background: #1ebbd9" height="30" @click="show = !show">
              <div class="d-flex align-center mx-5">
                <b class="white--text ma-3" style="font-size: 14px"
                  >Basic Details</b
                >
                <v-spacer></v-spacer
                ><v-icon class="white--text" v-show="show"
                  >mdi-plus-box-outline</v-icon
                >
                <v-icon class="white--text" v-show="!show"
                  >mdi-minus-box</v-icon
                >
              </div>
            </div>
            <div class="ml-0" v-show="!show">
              <v-form>
                <v-layout wrap class="pt-3 form-group-container">
                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="textSize">Countries Of Visa Application</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter"
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="font-weight-bold textSize">FIR Date</b
                      ><span class="red--text">*</span>
                    </label>
                    <v-menu
                      ref="menu"
                      v-model="menu"
                      :close-on-content-click="false"
                      :return-value.sync="date"
                      transition="scale-transition"
                      offset-y
                      min-width="auto"
                    >
                      <template v-slot:activator="{ on, attrs }">
                        <v-text-field
                          v-model="date"
                          placeholder="DD/MM/YYYY"
                          class="form-control rounded-0"
                          readonly
                          v-bind="attrs"
                          v-on="on"
                          solo
                          dense
                          outlined
                        >
                          <template v-slot:prepend-inner>
                            <v-icon class="iconstyle"> mdi-calendar </v-icon>
                          </template>
                        </v-text-field>
                      </template>
                      <v-date-picker v-model="date" no-title scrollable>
                        <v-spacer></v-spacer>
                        <v-btn text color="primary" @click="menu = false">
                          Cancel
                        </v-btn>
                        <v-btn
                          text
                          color="primary"
                          @click="$refs.menu.save(date)"
                        >
                          OK
                        </v-btn>
                      </v-date-picker>
                    </v-menu>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">To Country</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      counter="50"
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">From Country</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      counter="50"
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="font-weight-bold textSize">
                        Passport Number
                      </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter"
                      solo
                      counter="20"
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                </v-layout>

                <v-layout>
                  <v-card class="vcard rounded-0" id="card1" elevation="0">
                    <label class="subtitle-2"
                      ><b class="font-weight-bold textSize">
                        Reason of Rejection of Visa From Embassy </b
                      ><span class="red--text">*</span></label
                    >
                    <v-text-field
                      class="input"
                      solo
                      outlined
                      counter="200"
                      dense
                      label="Enter..."
                    ></v-text-field>
                  </v-card>
                  <v-card class="vcard rounded-0" id="card2" elevation="0">
                    <label class="subtitle-2"
                      ><b class="font-weight-bold textSize">
                        Is This An Accident Case? </b
                      ><span class="red--text">*</span></label
                    >
                    <v-select
                      class="input"
                      solo
                      outlined
                      dense
                      label="Enter..."
                    ></v-select>
                  </v-card>
                </v-layout>
              </v-form>
            </div>
          </div>
        </div>
      </div>
    </template>

    <template>
      <div class="mt-2">
        <div>
          <!-- basic details -->
          <div style="border: 1px solid grey">
            <div
              style="background: #1ebbd9"
              height="30"
              @click="show1 = !show1"
            >
              <div class="d-flex align-center mx-5">
                <b class="white--text ma-3" style="font-size: 14px"
                  >Accident Details</b
                >
                <v-spacer></v-spacer
                ><v-icon class="white--text" v-show="show1"
                  >mdi-plus-box-outline</v-icon
                >
                <v-icon class="white--text" v-show="!show1"
                  >mdi-minus-box</v-icon
                >
              </div>
            </div>
            <div class="ml-0" v-show="!show1">
              <v-form>
                <v-layout wrap class="pt-1 form-group-container">
                  <!-- ------------------------------ROW -1 ------------------------------ -->
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Nature Of Accident
                      </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-select
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-select>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">Others</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>

                  <v-flex class="form-group mt-3">
                    <label class="form-label ml-2"
                      ><b class="textSize">FIR Registered</b>
                      <span class="red--text">*</span>
                    </label>

                    <v-card
                      id="card3"
                      class="radio-btn-card ml-2 vcard rounded-0"
                      width="220px"
                      height="40%"
                      rounded="0"
                      outlined
                      elevation="2"
                    >
                      <v-radio-group
                        v-model="row"
                        row
                        class="radio-btn-grp pa-1 pt-2 pl-3"
                      >
                        <v-radio label="Yes" value="yes"></v-radio>

                        <v-radio label="No" value="no"></v-radio>
                      </v-radio-group>
                    </v-card>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Reason For Not Intimating Police
                      </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                      :counter="100"
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="font-weight-bold textSize"> FIR/GD Number </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                </v-layout>
                <!-- -----------------------------ROW -2 -------------------------- -->
                <v-layout wrap class="pt-1 form-group-container">
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">FIR Date</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-menu
                      ref="menu1"
                      v-model="menu1"
                      :close-on-content-click="false"
                      :return-value.sync="date"
                      transition="scale-transition"
                      offset-y
                      min-width="auto"
                    >
                      <template v-slot:activator="{ on, attrs }">
                        <v-text-field
                          v-model="date1"
                          placeholder="DD/MM/YYYY"
                          class="form-control rounded-0"
                          readonly
                          v-bind="attrs"
                          v-on="on"
                          solo
                          dense
                          outlined
                        >
                          <template v-slot:prepend-inner>
                            <v-icon class="iconstyle"> mdi-calendar </v-icon>
                          </template>
                        </v-text-field>
                      </template>
                      <v-date-picker v-model="date1" no-title scrollable>
                        <v-spacer></v-spacer>
                        <v-btn text color="primary" @click="menu1 = false">
                          Cancel
                        </v-btn>
                        <v-btn
                          text
                          color="primary"
                          @click="$refs.menu1.save(date1)"
                        >
                          OK
                        </v-btn>
                      </v-date-picker>
                    </v-menu>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Police Station Name
                      </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Police Station Address Line 1
                      </b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Police Station Address Line 2
                      </b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="font-weight-bold textSize">
                        Police Station Address Line 3
                      </b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                </v-layout>

                <!-- ------------------------------ROW-3-------------------------- -->
                <v-layout wrap class="pt-1 form-group-container">
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">Pincode</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">City</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">District</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">State</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label"
                      ><b class="font-weight-bold textSize">Phone</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      type="Number"
                      solo
                      dense
                      outlined
                    >
                      <template v-slot:prepend-inner>
                        <v-icon class="iconstyle"> mdi-phone </v-icon>
                      </template>
                    </v-text-field>
                  </v-flex>
                </v-layout>

                <!-- ----------------------------ROW -4----------------------------------- -->
                <v-layout wrap class="pt-1 form-group-container">
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">Email ID</b>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      prepend-inner-icon="mdi-email"
                      solo
                      dense
                      outlined
                    >
                      <template v-slot:prepend-inner>
                        <v-icon class="iconstyle"> mdi-email </v-icon>
                      </template>
                    </v-text-field>
                  </v-flex>

                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">MLC</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">MLC Number</b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                    ></v-text-field>
                  </v-flex>
                  <v-flex class="form-group1 ma-3">
                    <label class="form-label">
                      <b class="font-weight-bold textSize">
                        Accident Description
                      </b>
                      <span class="red--text">*</span>
                    </label>
                    <v-text-field
                      class="input"
                      label="Enter..."
                      solo
                      dense
                      outlined
                      :counter="100"
                    ></v-text-field>
                  </v-flex>
                </v-layout>
              </v-form>

              <div></div>
            </div>
          </div>
        </div>
      </div>
    </template>

    <v-card flat class="mt-4 mb-5">
      <v-layout>
        <v-btn
          class="mr-4"
          color="red"
          outlined
          flat
          style="width: 115px; height: 35px"
          ><v-icon>mdi-backspace-outline</v-icon
          ><v-divider vertical class="red mx-2"></v-divider>Reset</v-btn
        >

        <v-btn color="red" outlined flat style="width: 115px; height: 35px"
          ><v-icon>mdi-backspace-outline</v-icon
          ><v-divider vertical class="red mx-2"></v-divider>Cancel</v-btn
        >
        <v-spacer></v-spacer>
        <v-btn
          class="white--text"
          style="width: 115px; height: 35px; background: #23b1a9"
          ><v-icon>mdi-arrow-right-circle-outline</v-icon
          ><v-divider vertical class="mx-2"></v-divider> Submit</v-btn
        >
      </v-layout>
    </v-card>
  </div>
</template>

<script>
import "../assets/Main.css";
export default {
  name: "MainContent",
  data() {
    return {
      show: false,
      show1: false,
    
      b: 0,
      menu:false,
      date:'',
      menu1:false,
      date1:'',
     
    };
  },

  // methods: {
  //   display() {
  //     console.log("function calling");
  //     let a = document.getElementById("chan");

  //     if (this.b) {
  //       a.Style.visibility = "hidden";

  //       console.log(true);
  //       this.b = this.b - 1;
  //     } else {
  //       console.log(false);
  //       a.Style.visibility = "visible";
  //       this.b = this.b + 1;
  //     }
  //   },
  // },
};
</script>

<style scoped>
.input {
  border-radius: 0;
}
* {
  text-decoration: none !important;
}
.form-group {
  width: 220px;
}
.radio-btn-card {
  display: flex;

  align-items: center;

  justify-content: flex-start;
}
.form-group1 {
  width: 470px;
}
.form-group2 {
  width: 70px;
}

#card1 {
  width: 500px;
  margin: 0px 10px;
  border-radius: 0;
}

#card2 {
  width: 240px;
  margin: 0px 10px;
  border-radius: 0;
}
#card3 {
  border: 1px solid gray;
}
.iconstyle {
  display: flex;
  align-items: center;
  justify-content: center;
  border-right: 1px solid #c1c8cc;
  background-color: #f7f7f7;
  height: 40px;
  width: 40px;
  margin-left: -12px;
}
</style>
