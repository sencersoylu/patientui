<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        Patient Search Panel
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <v-row class="justify-center">
        <v-col cols="12" md="9">
          <PatientSearchPanel />
        </v-col>
      </v-row>
      <v-row class="justify-center">
        <v-col cols="12" md="10">
          <PatientTable />
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import PatientSearchPanel from './components/PatientSearchPanel';
import PatientTable from './components/PatientTable';

export default {
  name: 'App',

  components: {
    PatientSearchPanel,
    PatientTable,
  },

  data: () => ({
    //
  }),
  mounted() {
    const params = new URLSearchParams();
    params.append('username', 'ngs');
    params.append('password', 'ngs');

    this.axios.post(
      'https://empitest.smhd.sanmateocounty.ads:8443/ws/auth/auth/authenticate',
      params,
      {
        withCredentials: true,
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded',
        },
      }
    );
  },
};
</script>
