<template>
  <v-app>
    <div>
      <v-app-bar color="#10242B" dense dark flat app>
        <v-btn icon>
          <v-icon color="#20B2AA" large>mdi-arrow-left-circle</v-icon>
        </v-btn>
        <p class="text-h5  ml-5 mt-3 white--text headColour" style="font-size:16px ;">
          Add Assessment Sheet
        </p>
        <v-spacer></v-spacer>
        <p class="text-h6 mt-3 white--text">Close</p>
      </v-app-bar>
    </div>
    <!-- ----------------------POLITICAL RISK CLAIM --------------------------->
    <template>
      <v-title class="mb-2">
        <h2>Add Details to assessment sheet</h2>
      </v-title>
      <!-- -------------------BASIC DETAILS-------------------------------- -->
      <div class="expansion-panel-container">
        <div class="expansion-panel-header" @click="isToggle = !isToggle">
          <div style="font-size: 14px;">Basic Details</div>
          <v-spacer></v-spacer>

          <div @click="isToggle = !isToggle">
            <v-icon v-show="isToggle" class="white--text">mdi-plus-box</v-icon>
            <v-icon v-show="!isToggle" class="white--text">
              mdi-minus-box</v-icon
            >
          </div>
        </div>
        <div v-show="!isToggle">
          <v-form>
            <!-- ------------------------------ROW -1-------------------------------------- -->
            <v-layout wrap class="pt-4 form-group -container">
              <v-flex class="form-group ma-3">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Settlement Type</b
                  >
                  <span class="red--text">*</span>
                </label>
                <v-select
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                  :counter="50"
                ></v-select>
              </v-flex>

              <v-flex class="form-group ma-3">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Claim Payment Type</b
                  >
                  <span class="red--text">*</span>
                </label>
                <v-select
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                  :counter="50"
                ></v-select>
              </v-flex>
              <v-flex class="form-group ma-3">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Transaction Type</b
                  >
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
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Country Name</b
                  >
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
                  <b class="font-weight-bold" style="font-size: 13px">
                    Currency Name</b
                  >
                  <span class="red--text">*</span></label
                >
                <v-select
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                ></v-select>
              </v-flex>
            </v-layout>

            <!-- ----------------------------------ROW - 2------------------------------------ -->

            <v-layout>
              <v-card class="vcard rounded-0" elevation="0">
                <label class="subtitle-2"
                  ><b class="font-weight-bold " style="font-size: 13px"> Rate Of Exchange </b
                  ><span class="red--text">*</span></label
                >
                <v-text-field
                  class="input"
                  solo
                  outlined
                  disabled
                  dense
                  label="Enter..."
                ></v-text-field>
              </v-card>

              <v-card class="vcard rounded-0" elevation="0">
                <label class="subtitle-2"
                  ><b class="font-weight-bold " style="font-size: 13px">
                    Rate Of Exchange Date</b
                  ><span class="red--text">*</span></label
                >
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
                    <v-btn text color="primary" @click="$refs.menu.save(date)">
                      OK
                    </v-btn>
                  </v-date-picker>
                </v-menu>
              </v-card>

              <v-card class="vcard rounded-0" elevation="0">
                <label class="subtitle-2"
                  ><b class="font-weight-bold " style="font-size: 13px">
                    ROE Updated Manually </b
                  ><span class="red--text">*</span></label
                >
                <v-select
                  class="input"
                  disabled
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
    </template>
    <!-- -----------------------------Amount Details--------------------------------------------- -->
    <template>
      <div class="expansion-panel-container">
        <div class="expansion-panel-header" @click="isToggle1 = !isToggle1">
          <div style="font-size: 14px;">Amount Details</div>
          <v-spacer></v-spacer>

          <div>
            <v-icon v-show="isToggle1" class="white--text">mdi-plus-box</v-icon>
            <v-icon v-show="!isToggle1" class="white--text"
              >mdi-minus-box</v-icon
            >
          </div>
        </div>

        <div v-show="!isToggle1">
          <v-form>
            <v-layout wrap class="pt-4 form-group-container">
              <!-- ------------------------------ROW -1 ------------------------------ -->
              <v-flex class="form-group ma-2">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Deductible Amount</b
                  >
                </label>
                <v-select
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                ></v-select>
              </v-flex>

              <v-flex class="form-group ma-2">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px">Copay%</b>
                </label>
                <v-text-field
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                ></v-text-field>
              </v-flex>
              <v-flex class="form-group ma-2">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Claimed Amount</b
                  >
                </label>
                <v-select
                  class="input"
                  label="Enter..."
                  solo
                  dense
                  outlined
                ></v-select>
              </v-flex>
              <v-flex class="form-group ma-2">
                <label class="form-label">
                  <b class="font-weight-bold" style="font-size: 13px"
                    >Amount Payable</b
                  >
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
              <v-flex class="form-group ma-2">
                <label class="form-label"
                  ><b class="font-weight-bold" style="font-size: 13px"
                    >Net Payable</b
                  >
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
          </v-form>
        </div>
      </div>
    </template>

    <!-- -----------------------------Non- payable Expanses--------------------------------------------- -->
    <template>
      <div class="expansion-panel-container">
        <div class="expansion-panel-header" @click="isToggle2 = !isToggle2">
          <div style="font-size: 14px;">Non- Payable Expanses</div>
          <v-spacer></v-spacer>

          <div>
            <v-icon v-show="isToggle2" class="white--text">mdi-plus-box</v-icon>
            <v-icon v-show="!isToggle2" class="white--text"
              >mdi-minus-box</v-icon
            >
          </div>
        </div>

        <div v-show="!isToggle2">
          <div style="width: 98%; margin: 0 auto">
            <v-form>
              <v-layout wrap class="pt-4 form-group-container">
                <!-- ------------------------------ROW -1 ------------------------------ -->
                <v-flex
                  lg2
                  class="form-group expense-input ma-2"
                  style="height: 40px"
                >
                  <v-checkbox
                    class="input"
                    label="Non payable Expense"
                    solo
                    dense
                    outlined
                  >
                  </v-checkbox>
                </v-flex>
              </v-layout>
            </v-form>

            <v-card elevation="2" class="mx-3 mt-5" flat>
              <v-data-table
                elevation="2"
                id="tabl"
                disable-filtering
                disable-pagination
                disable-sort
                hide-default-footer
                :items="item"
                :headers="headers"
                tellclass="kar"
              >
                <template v-slot:[`headers.invoice`]="{ headers }">
                  <th style="color: #23b1a9"></th>
                  {{ headers.text }}
                </template>
                <template v-slot:[`item.invoice`]="{ item }">
                  <v-text-field
                    label="1000"
                    outlined
                    dense
                    class="mt-2 input"
                    style="align-text: center"
                  ></v-text-field
                  >{{ item.text }}
                </template>
                <template v-slot:[`item.invoicedate`]="{ item }">
                  <v-text-field
                    label="1000"
                    outlined
                    dense
                    class="mt-2 input"
                    style="align-text: center"
                  ></v-text-field
                  >{{ item.text }}
                </template>
                <template v-slot:[`item.invoicedetails`]="{ item }">
                  <v-text-field
                    label="1000"
                    outlined
                    dense
                    class="mt-2 input"
                    style="align-text: center"
                  ></v-text-field
                  >{{ item.text }}
                </template>
                <template v-slot:[`item.invoiceamount`]="{ item }">
                  <v-text-field
                    label="1000"
                    outlined
                    dense
                    class="mt-2 input"
                    style="align-text: center"
                  ></v-text-field
                  >{{ item.text }}
                </template>
                <template v-slot:[`item.action`]="{ item }">
                  <v-icon class="red--text">mdi-delete</v-icon>{{ item.text }}
                </template>
              </v-data-table>
            </v-card>

            <div class="add-row-icon mt-4" id="addbtn">
              <span><v-icon class="white green--text"> mdi-plus </v-icon></span>
              <span class="white green--text"> Add Row </span>
            </div>

            <!-- -------------------------total non payable amount---------------------------- -->
            <v-form>
              <v-layout wrap class="pt-4 form-group-container">
                <!-- ------------------------------ROW -1 ------------------------------ -->
                <v-flex lg2 class="form-group ma-2">
                  <label class="form-label">
                    <b class="font-weight-bold" style="font-size: 13px"
                      >Total Non-Payable Amount</b
                    >
                  </label>
                  <v-text-field class="input" label="Enter" solo dense outlined>
                  </v-text-field>
                </v-flex>
              </v-layout>
            </v-form>
          </div>
        </div>
      </div>

      <!-- ----------------------BUTTONS SECTION-------------------------------- -->
      <!-- --------------------------BUTTONS---------------------------------- -->
      <v-card class="mt-4 mb-10" flat>
        <v-layout>
          <v-btn class="mr-4" color="red" outlined flat
            ><v-icon>mdi-backspace-outline</v-icon
            ><v-divider vertical class="red mx-2"></v-divider>Reset</v-btn
          >

          <v-spacer></v-spacer>

          <v-btn class="mx-2" color="red" outlined flat
            ><v-icon>mdi-backspace-outline</v-icon
            ><v-divider vertical class="red mx-2"></v-divider>Cancel</v-btn
          >

          <v-btn id="btn" class="white--text" to="/PoliticalRiskSheet"
            ><v-icon>mdi-arrow-right-circle-outline</v-icon
            ><v-divider vertical class="white mx-2"></v-divider> Submit</v-btn
          >
        </v-layout>
      </v-card>
    </template>
  </v-app>
</template>

<script>
import "../assets/Main.css";
export default {
  name: "AddAssessmentSheet",
  data() {
    return {
      isToggle: false,
      isToggle1: false,
      isToggle2: true,
      headers: [
        {
          text: "Serial Number",
          align: "center",
          value: "serialn",
          class: " white--text",
          id: "bgcolor",
          width: 100,
        },
        {
          text: "Invoice Number",
          value: "invoice",
          class: " white--text",
          align: "center",
          width: 150,
        },
        {
          text: "Invoice Date",
          value: "invoicedate",
          class: " white--text",
          width: 250,
          align: "center",
        },
        {
          text: "Invoice Details",
          value: "invoicedetails",
          class: " white--text",
          width: 350,
          align: "center",
        },
        {
          text: "Invoice Amount",
          value: "invoiceamount",
          class: " white--text",
          width: 150,
          align: "center",
        },
        {
          text: "Action",
          value: "action",
          class: " white--text",
          width: 150,
          align: "center",
        },
      ],
      item: [
        {
          serialn: "002434234",
        },
      ],
    };
  },
};
</script>

<style>
#addbtn {
  margin-left: 49%;
}
.input {
  border-radius: 0px !important;
}
.expansion-panel-header {
  display: flex;
  align-items: center;
  background-color: #1ebbd9;
  color: white;
  height: 60px;
  padding: 20px;
}
.expansion-panel-container {
  margin-top: 10px;
  border: 1px solid rgb(166, 160, 160);
}
.expense-input {
  border: 1px solid grey;
}
.v-data-table-header tr {
  background-color: #23b1a9;
}
.v-data-table-header tr th {
  border: 1px solid #c1c8cc;
}

.v-data-table__wrapper table tbody tr td {
  border-left: 1px solid #c1c8cc;
  height: 20px;
}
.vcard {
  width: 240px;
  margin: 0px 10px;
  border-radius: none;
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
