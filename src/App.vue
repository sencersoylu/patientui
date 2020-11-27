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
import qs from 'qs';

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
    var data = qs.stringify({
      username: 'ngs',
      password: 'ngs',
    });
    var config = {
      method: 'post',
      url:
        'https://empitest.smhd.sanmateocounty.ads:8443/ws/auth/auth/authenticate',
      headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
        Cookie:
          'JSESSIONID=14sc4ivj6tyuw1a2g41cukjwfg; XSRF-TOKEN="iJ1I/pxFjd0n04WhzhbC/EEd01s/VsS9lgTOnS/gllY="',
      },
      data: data,
    };

    this.axios(config)
      .then(function(response) {
        console.log(JSON.stringify(response.data));
      })
      .catch(function(error) {
        console.log(error);
      });
  },
};
</script>
