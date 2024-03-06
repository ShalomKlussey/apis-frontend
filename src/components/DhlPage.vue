<template>
  <v-app>
    <v-container class="background">
      <v-row justify="center">
        <v-col cols="12" sm="8" md="4">
          <!-- Search bar -->
          <v-card class="mx-auto" color="grey-lighten-3" max-width="400">
            <v-card-text>
              <v-text-field v-model="sendingId" :loading="loading" append-inner-icon="mdi-magnify" density="compact"
                label="Sending ID" variant="solo" hide-details single-line @click:append-inner="onClick"></v-text-field>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="12" sm="8" md="4">
          <v-card>
            <v-card-title class="headline">Address</v-card-title>
            <v-card-text>
              <v-form @submit.prevent="sendNeuEmail">
                <v-text-field v-model="name" label="Full Name" variant="underlined" required></v-text-field>
                <v-text-field v-model="address" label="Address" variant="underlined" required></v-text-field>
                <v-text-field v-model="city" label="City" variant="underlined" required></v-text-field>
                <v-text-field v-model="region" label="Region" variant="underlined" required></v-text-field>
                <v-text-field v-model="zip" label="Postal Code" variant="underlined" required></v-text-field>
                <v-text-field v-model="country" label="Country" variant="underlined" required></v-text-field>

                <v-checkbox v-model="terms" color="secondary" label="I agree to terms and conditions"></v-checkbox>
              </v-form>
            </v-card-text>
            <v-divider></v-divider>

            <v-card-actions>
              <v-btn>Cancel</v-btn>
              <v-spacer></v-spacer>

              <v-btn color="success">
                Send to CPA

                <v-icon icon="mdi-chevron-right" type="submit" end></v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>

    </v-container>
    <v-footer>
      <div class="px-4 py-2 bg-black text-center w-100">
        <strong>© 2024 CPA SoftwareConsult GmbH</strong>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DhlPage',
  data() {
    return {
      sendingId: '',
      searchResults: [],
      terms: false,
      loaded: false,
      loading: false,

      name: '',
      address: '',
      city: '',
      region: '',
      zip: '',
      country: ''
    };
  },
  methods: {
    search() {


      // Perform search logic here, for now, let's just simulate some results
      this.searchResults = [
        { id: 1, title: 'Search Result 1', description: 'Description of search result 1' },
        { id: 2, title: 'Search Result 2', description: 'Description of search result 2' },
        { id: 3, title: 'Search Result 3', description: 'Description of search result 3' }
      ];
    },
    sendNeuEmail() {

    },
    onClick() {
      this.loading = true

      setTimeout(() => {
        this.loading = false
        this.loaded = true
      }, 2000)

      this.name = 'Client One',
        this.address = 'BrinckmannStr. 52',
        this.city = 'Düsseldorf',
        this.region = 'NRW',
        this.zip = '40225',
        this.country = 'Deutschland'
    },
  }
};
</script>

<style>
.background {
  /* Set background image */
  background-image: url('/images/cpa-Vorteil-BG.jpg');
  /* Ensure the image covers the entire screen */
  background-size: cover;
  /* Center the image */
  background-position: center;

  height: 100%;
  width: 100%;
}
</style>