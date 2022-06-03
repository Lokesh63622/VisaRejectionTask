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
    <div class="d-flex justify-lg-space-between align-center">
      <div class="font-weight-bold ma-4">Political Risk Assessment Sheets</div>
      <div>
        <v-btn
          to="/AddAssessmentSheet"
          id="img"
          class="light-blue white--text text-caption"
          ><v-icon>mdi-plus-box-outline</v-icon>
          <v-divider vertical class="mx-3 grey lighten-5"></v-divider>
          Add Assessment</v-btn
        >
      </div>
    </div>
    <div>
      <v-data-table
        id="tabl"
        disable-filtering
        disable-pagination
        disable-sort
        hide-default-footer
        :items="items"
        :headers="headers"
      >
      <template v-slot:[`item.action`]="{ item }">
  <v-icon small class="black--text">mdi-dots-vertical</v-icon>{{ item.text }}
</template>
      </v-data-table>
    </div>
  </div>
</template>

<script>
export default {
  name: "PoliticalRiskSheet",
  data() {
    return {
      items: [
        {
         
          Settlement: "Standard",
          Claim: "Cashless to the insured",
          Transaction: "Partial Payment",
          Disability: "0",
          Deductible: "11,600",
          Time: "11:00",
          Copay: "0",
          PerDay: "1500",
          Maxno: "6",
          Claimed: "24,000",
          Amount: "12,400",
          Net: "12,400",
          Total: "24,000",
          TotalNon: "11,600",
        },
        {
         
          Settlement: "Standard",
          Claim: "Cashless to the insured",
          Transaction: "Partial Payment",
          Disability: "0",
          Deductible: "11,600",
          Time: "11:00",
          Copay: "0",
          PerDay: "1500",
          Maxno: "6",
          Claimed: "24,000",
          Amount: "12,400",
          Net: "12,400",
          Total: "24,000",
          TotalNon: "11,600",
        },
      ],
      headers: [
        {
          text: "Action",
          align: "start",
          value: "action",
          class: "teal white--text border-left:1px solid black",
          style: "",
          width: 50,
        },
        {
          text: "Settlement Type",
          value: "Settlement",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Claim Payment Type",
          value: "Claim",
          class: "teal white--text",
          width: 200,
        },
        {
          text: "Transaction Type",
          value: "Transaction",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Disability Amount",
          value: "Disability",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Deductible Amount",
          value: "Deductible",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Time Deductible (In Hours)",
          value: "Time",
          class: "teal white--text",
          width: 200,
        },
        {
          text: "Copay%",
          value: "Copay",
          class: "teal white--text",
          width: 50,
          border: 1,
        },
        {
          text: "Per Day Maximum",
          value: "PerDay",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Max no. of days Payable",
          value: "Maxno",
          class: "teal white--text",
          width: 200,
        },
        {
          text: "Claimed Amount",
          value: "Claimed",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Amount Payable",
          value: "Amount",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Net Payable",
          value: "Net",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Total Invoice Amount",
          value: "Total",
          class: "teal white--text",
          width: 150,
        },
        {
          text: "Total Non Payable Amount",
          value: "TotalNon",
          class: "teal white--text",
          width: 200,
        },
      ],
    };
  },
};
</script>

<style scoped>
#tabl.v-data-table.tbody.td {
  border: 1px solid;
}
</style>
