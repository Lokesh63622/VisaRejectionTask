<template>
  <div>
    <v-app-bar color="#10242B" dense dark flat app>
      <v-btn icon>
       <v-icon color="#20B2AA"  large >mdi-arrow-left-circle</v-icon>
      </v-btn>

      <v-toolbar-title>Claim Processing</v-toolbar-title>
      <v-icon class="ml-8 align-center">mdi-menu-down</v-icon>
      <v-spacer></v-spacer>
      <v-icon color="#23B1A9">mdi-lightning-bolt</v-icon>
      <v-toolbar-title class="body-2 mr-3">Quick Menu</v-toolbar-title>

      <v-icon color="#23B1A9">mdi-file-document-outline</v-icon>
      <v-toolbar-title class="body-2 mr-3"
        >View/Upload Documents</v-toolbar-title
      >

      <v-icon color="#23B1A9">mdi-dots-vertical</v-icon>
      <v-toolbar-title class="body-2">Menu</v-toolbar-title>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    items: [
      { title: "FNOL/Registretion" },
      { title: "Reserve Details" },
      { title: "Service Provider Appointment" },
      { title: "Claim Processing &Assessment" },
      { title: "Payment" },
      { title: "Claim Summary" },
    ],
    drops: [
      { title: "Transaction History" },
      { title: "Feature Activity" },
      { title: "Notes" },
      { title: "Audit Trail" },
      { title: "Co-insurence Summary" },
    ],

    Menu: [
      { title: "Examinetion Checklist" },
      { title: "First Contact" },
      { title: "Query" },
      { title: "OFR" },
    ],
  }),
};
</script>

<style scoped></style>
