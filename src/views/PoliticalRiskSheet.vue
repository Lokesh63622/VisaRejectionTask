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
        <v-btn
          to="/"
          class="pa-4 ml-0 text-subtitle-2"
          style="text-transform: none"
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
        id="table"
        hide-default-footer
        disable-sort
        :items="items"
        :headers="headers"
      >
        <template v-slot:[`item.action`]="{}">
          <v-menu offset-y>
            <template v-slot:activator="{ on, attrs }">
              <v-icon flat slot="activator" v-bind="attrs" v-on="on" left
                >mdi-dots-vertical</v-icon
              >
            </template>
            <v-list  v-for="link in links"
                :key="link.text"
              style="border:1px solid #C1C8CC;" >
              <v-list-item
                style="min-height: 20px; width:130px;"
              >
                <template
                  v-if="link.text === 'Modify'"
                   
                >
                  <v-icon class="pr-3">mdi-{{ link.icon }}</v-icon>
                  <v-list-item-title class="teal--text">{{
                    link.text
                  }}</v-list-item-title>
                </template>
                <template v-else>
                  <v-icon class="pr-3">mdi-{{ link.icon }}</v-icon>
                  <v-list-item-title>{{ link.text }}</v-list-item-title>
                </template>
              </v-list-item>
            </v-list>
          </v-menu>
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
          class: " white--text ",
          style: "",
          width: 50,
        },
        {
          text: "Settlement Type",
          value: "Settlement",
          class: " white--text",
          width: 150,
        },
        {
          text: "Claim Payment Type",
          value: "Claim",
          class: " white--text",
          width: 200,
        },
        {
          text: "Transaction Type",
          value: "Transaction",
          class: " white--text",
          width: 150,
        },
        {
          text: "Disability Amount",
          value: "Disability",
          class: " white--text",
          width: 150,
        },
        {
          text: "Deductible Amount",
          value: "Deductible",
          class: " white--text",
          width: 150,
        },
        {
          text: "Time Deductible (In Hours)",
          value: "Time",
          class: " white--text",
          width: 200,
        },
        {
          text: "Copay%",
          value: "Copay",
          class: " white--text",
          width: 50,
          border: 1,
        },
        {
          text: "Per Day Maximum",
          value: "PerDay",
          class: " white--text",
          width: 150,
        },
        {
          text: "Max no. of days Payable",
          value: "Maxno",
          class: " white--text",
          width: 200,
        },
        {
          text: "Claimed Amount",
          value: "Claimed",
          class: " white--text",
          width: 150,
        },
        {
          text: "Amount Payable",
          value: "Amount",
          class: " white--text",
          width: 150,
        },
        {
          text: "Net Payable",
          value: "Net",
          class: " white--text",
          width: 150,
        },
        {
          text: "Total Invoice Amount",
          value: "Total",
          class: " white--text",
          width: 150,
        },
        {
          text: "Total Non Payable Amount",
          value: "TotalNon",
          class: " white--text",
          width: 200,
        },
      ],
    links: [
        { icon: "eye", text: "View" },
        { icon: "pencil-outline", text: "Modify" },
      ],
      offset: true,
    };
  },
};
</script>

<style >
#tabl.v-data-table.tbody.td {
  border: 1px solid;
}

.v-data-table-header tr{
  background-color:#23B1A9;
 
}
.v-data-table-header tr th{
 border:1px solid #C1C8CC;
 font-size:14px;
 font-weight:bold
}
/* .kar{
  border:1px solid black
} */
.v-data-table__wrapper table tbody tr td{
   border-left:1px solid #C1C8CC;
   height:20px
}
</style>
