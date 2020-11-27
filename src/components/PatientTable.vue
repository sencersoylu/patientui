<template>
  <v-card elevation="4" class="mt-4">
    <v-simple-table>
      <template v-slot:default>
        <thead>
          <tr>
            <th class="text-left">
              Name
            </th>
            <th class="text-left">
              Surname
            </th>
            <th class="text-left">
              Gender
            </th>
            <th class="text-left">
              DOB
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in 15" :key="item">
            <td>pastaface</td>
            <td>test</td>
            <td>Male</td>
            <td>3/19/1968</td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>
  </v-card>
</template>

<script>
export default {};
</script>

<style></style>
